# About
A Java Library for querying Steam's servers.
Created with:
- [Master Server Query Protocol](https://developer.valvesoftware.com/wiki/Master_Server_Query_Protocol)
- [Server Queries](https://developer.valvesoftware.com/wiki/Server_queries)

# How to include in another projects
#### pom.xml

    <dependencies>
        ...
        <dependency>
            <groupId>com.github.boubari97</groupId>
            <artifactId>steam-servers-requester</artifactId>
            <version>1.0</version>
        </dependency>
        ...
    </dependencies>
    ...
    <repositories>
        ...
        <repository>
            <id>steam-query-java-mvn-repo</id>
            <url>https://raw.github.com/Boubari97/steam-servers-requester/mvn-repo/</url>
            <snapshots>
                <enabled>true</enabled>
                <updatePolicy>always</updatePolicy>
            </snapshots>
        </repository>
        ...
    </repositories>

## Usage
#### Getting a list of Rust servers

    MasterServer masterServer = new MasterServer();
    QueryFilterBuilder builder = new QueryFilterBuilder().game("rust").build();
    masterServer.requestServers(builder);

#### Getting a server by ip and query port
Also, query port is port + 1. For example: port is 50110, query port is 50111.

    GameServer server = new GameServer("0.0.0.0", 50111);

#### Update server data
    server.updateServerData();