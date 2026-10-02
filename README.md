# ETH002 POSIX C example

This is a simple utility written in for POSIX C that can be used to connect to
an ETH002, and then read or set the state of the relay outputs.

The ETH002 is a Ethernet connected module that provides 2 volt free contact
relay outputs. It has a simple TCP/IP control interface, and MQTT support with
TLS encryption. More details can be found [on our
website.](https://www.robot-electronics.co.uk/eth002b.html)

## Compile

## Build the program

Build the program with the following command in a release setup:

```
cmake -DCMAKE_BUILD_TYPE=Release -B build-release/ && make -C build-release
```

Alternatively as debug build:

```
cmake -DCMAKE_BUILD_TYPE=Debug  -B build-debug/ && make -C build-release
```

## Usage

In the following replace `<port>`, `<password>` and `<ip>` with the port
number, password, and IP address of your module.

Toggle relay number 1.
```
eth002 -t 1 -P <password> -p <port> <ip> 
```


