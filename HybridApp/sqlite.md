# Cordova-sqlite-storage

[Cordova-sqlite-storage](https://github.com/litehelpers/Cordova-sqlite-storage) on Github.

## 安装插件

	cordova plugin add Cordova-sqlite-storage

## 使用方法

#### Echo test

To verify that both the Javascript and native part of this plugin are installed in your application:

```javascript

	window.sqlitePlugin.echoTest(successCallback, errorCallback);

```

#### Opening a database

Recommended: 

```javascript

	var db = window.sqlitePlugin.openDatabase({name: "my.db", location: 1}, successcb, errorcb);

```

The location option is used to select the database subdirectory location (iOS only) with the following choices:

0 (default): Documents - visible to iTunes and backed up by iCloud
1: Library - backed up by iCloud, NOT visible to iTunes
2: Library/LocalDatabase - NOT visible to iTunes and NOT backed up by iCloud

#### SQL transactions

- Single-statement transactions

Sample:

```javascript

	db.executeSql("SELECT LENGTH('tenletters') AS stringlength", [], function (res) {
		console.log('got stringlength: ' + res.rows.item(0).stringlength);
	}, function(error) {
		console.log('SELECT error: ' + error.message);
	});

```

- SQL batch query transactions

Sample:

```javascript

	db.sqlBatch([
	  'DROP TABLE IF EXISTS MyTable',
	  'CREATE TABLE MyTable (SampleColumn)',
	  [ 'INSERT INTO MyTable VALUES (?)', ['test-value'] ],
	], function() {
	  db.executeSql('SELECT * FROM MyTable', [], function (res) {
	    console.log('Sample column value: ' + res.rows.item(0).SampleColumn);
	  });
	}, function(error) {
	  console.log('Populate table error: ' + error.message);
	});

```

In case of an error, all changes in a sql batch are automatically discarded using ROLLBACK.

- Standard asynchronous transactions

Standard asynchronous transactions follow the HTML5/Web SQL API which is very well documented and uses BEGIN and COMMIT or ROLLBACK to keep the transactions failure-safe. Here is a very simple example from the test suite:

```javascript

	db.transaction(function(tx) {
	  tx.executeSql("SELECT UPPER('Some US-ASCII text') AS uppertext", [], function(tx, res) {
	    console.log("res.rows.item(0).uppertext: " + res.rows.item(0).uppertext);
	  }, function(error) {
	    console.log('SELECT error: ' + error.message);
	  });
	}, function(error) {
	  console.log('transaction error: ' + error.message);
	}, function() {
	  console.log('transaction ok');
	});

```

In case of a read-only transaction, it is possible to use readTransaction which will not use BEGIN, COMMIT, or ROLLBACK:

```javascript

	db.readTransaction(function(tx) {
	  tx.executeSql("SELECT UPPER('Some US-ASCII text') AS uppertext", [], function(tx, res) {
	    console.log("res.rows.item(0).uppertext: " + res.rows.item(0).uppertext);
	  }, function(error) {
	    console.log('SELECT error: ' + error.message);
	  });
	}, function(error) {
	  console.log('transaction error: ' + error.message);
	}, function() {
	  console.log('transaction ok');
	});

```