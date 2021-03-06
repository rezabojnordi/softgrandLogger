# softgrandLogger
Logger Interface for use in Node JS projects

<img src="http://uupload.ir/files/bkv5_softgrand.png"></img>

## Lager Features:
Logging in the Mongo database

Storing logs in json file system

Display error messages in red and specify the error line number

Show alerts in red

Can be configured to save logs or not

**config using logger**
```
let softgrandLogger = require('../index');
let Logger = new softgrandLogger({});

test = new Logger({
  model: {
    info: {
      type: JSON
    },
    message: {
      type: JSON
    },
    type: {
      type: String
    },
    time: {
      type: JSON
    },
    function: {
      type: JSON
    },
    stack: {
      type: JSON
    },
    additionalInfo: {
      type: JSON
    }
    
  },
  levelConfig: {
    warning: {
      save: true,
      color: 'yellowBg',
      show: true,
      viewPath: true
    },
    error: {
      save: false,
      color: 'redBg',
      show: true,
      view: {
        main: true,
        additionalView: false
      },
      viewPath: true
    },
    info: {
      save: true,
      show: true,
      viewPath: true
    }
  },
  storageDB: {
    fileSystem: {
      enabled: false

    },
    mongoDB: {
      enabled: false
     // partMongoInterfaceConfig: mongoInterfaceConfig
    }
  }

});



```

***using logger for project***
```

var e = {
  info: {
    sourceType: 'code',
    sourceName: '1'
  },
  message: {
    en: 'text message',
    fa: 'متن فارسی'
  }
};


//test.error(e,'reza');
//test.info(e,"yes of cource");
//test.info(e);
test.warning(e, {
  test: 456,
  test2: {
    test: 456,
    test3: {
      test: 456
    }
  }
});
