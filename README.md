# freechat
Free Chat is a cross-platform socket chat application, which uses [ezyfox-server](https://github.com/youngmonkeys/ezyfox-server) and it's client SDKs

> Official site: [https://youngmonkeys.org/freechat/](https://youngmonkeys.org/asset/freechat/)

# Supports

- ReactJS
- Android Java
- Android Kotlin (developing)
- iOS swift (developing)

# Usage

## ReactJS build
 
 1. Clone source code
 2. Move to ```reactjs``` folder
 3. Run ```npm start```
 
## Android build
 
 Required environment:
 
 ```
 - Android studio: 3.5
 - Gradle: 3.5.0 or 5.4.1
 - Android sdk: 26
 ```
 
 1. Clone source code
 2. Move to ```android/socket``` folder
 3. Clone ```ezyfox-server-android-client``` by commands:
 
 ```bash
git init
git remote add origin https://github.com/youngmonkeys/ezyfox-server-android-client.git
git pull origin master
```

4. Import project to ```Android studio```
5. Build and done

## iOS build

1. Clone source code
2. Move to ```swift/client```
3. Clone ```ezyfox-server-swift-client``` by commands:

```bash
git init
git remove add origin https://github.com/youngmonkeys/ezyfox-server-swift-client.git
git pull origin master
```

4. Move to ```swift/client/socket```
5. Clone ```ezyfox-server-cpp-client``` by commands:

```bash
git init
git remote add origin https://github.com/youngmonkeys/ezyfox-server-cpp-client.git
git pull origin master
``` 

6. Open project on ```XCode```
7. Build and run

## Server-side build and run

1. Install mongodb ([Tutorial](https://docs.mongodb.com/manual/administration/install-community/))
2. Create `freechat` db in mongodb ([Tutorial](https://www.mongodb.com/basics/create-database))
3. Create `root` user using mongo shell:
```
	use freechat
	db.createUser(
	   {
	     user:"root",
	     pwd:"123456”,
	     roles:[ { role: "readWrite", db: "freechat" }]
	   }
	)
```
> Update `server/freechat-plugin/config/config.properties` file to use another password
4. Clone source code
5. Import ```server``` folder into an IDE (Eclipse, Intellij, Netbean)
6. Run file [FreechatStartup](https://github.com/youngmonkeys/freechat/blob/master/server/freechat-startup/src/main/java/com/tvd12/freechat/FreechatStartup.java)
> The server opens a websocket at `ws://localhost:2208/ws`

# References
1. [Use embedded ezyfox-server](https://youngmonkeys.org/use-embedded-server/)
2. [Use ES6 client sdk](https://youngmonkeys.org/ezyfox-es6-client-sdk/)
3. [User to ezydata-mongodb](https://youngmonkeys.org/introduce-to-ezymongo/)

# License

Apache License, Version 2.0
