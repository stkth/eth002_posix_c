# ETH002 POSIX C example

This is a simple utility written in for POSIX C that can be used to connect to an ETH002, and then read or set the state of the relay outputs.

The ETH002 is a Ethernet connected module that provides 2 volt free contact relay outputs. It has a simple TCP/IP control interface, and MQTT support with TLS encryption. More details can be found [on our website.](https://www.robot-electronics.co.uk/eth002b.html)

## Compile
```
gcc -std=c99 -pedantic -o e002 eth002.c
```

## Usage

In the following replace `<port>`, `<password>` and `<ip>` with the port number, password, and IP address of your module.

Toggle relay number 1.
```
eth002 -t 1 -P <password> -p <port> <ip> 
```

## Set channels to active or inactive

Toggling of relays can be ineffective in certain circumstances, especially when
a certain guarantee of a required state is needed.

Instead of toggling, use the dedicated state and channel flags.

### Set channel one to high

```
eth002 -c 1 -s 1 <password> -p <port> <ip>
```

### Set channel one to inactive

```
eth002 -c 1 -s 0 <password> -p <port> <ip>
```
