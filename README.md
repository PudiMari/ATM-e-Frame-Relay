### Instituto Federal de Mato Grosso

Estudante: Mariana Dias do Espirito Santo

Matrícula: 2019178440380

Curso: Engenharia da Computação

Disciplina: Redes de Computadores II

---
# Configuração da rede ATM e Frame Relay

![topology](https://github.com/PudiMari/ATM-e-Frame-Relay/blob/main/Topologia.png?raw=true)

## Rede ATM

As configurações dos roteadores é como segue:

### R1:
```
configure terminal
int atm1/0
int atm1/0.100 point-to-point
ip address 10.0.1.1 255.255.255.0
pvc 100/101
protocol ip 10.0.1.2 broadcast
encapsulation aal5snap
no shutdown 
end
```

#### R2:
```
configure terminal
int atm1/0
int atm1/0.100 point-to-point
ip address 10.0.1.2 255.255.255.0
pvc 100/201
protocol ip 10.0.1.1 broadcast
encapsulation aal5snap
no shutdown 
end
```

### ATMSW1:

![atm1.png](https://github.com/PudiMari/ATM-e-Frame-Relay/blob/main/ATMSW1.png?raw=true)


### ATMSW2:
![atm2.png](https://github.com/PudiMari/ATM-e-Frame-Relay/blob/main/ATMSW2.png?raw=true)


### ATMSW3:
![atm3.png](https://github.com/PudiMari/ATM-e-Frame-Relay/blob/main/ATMSW3.png?raw=true)


## Rede Frame Relay

As configurações dos roteadores é como segue:

### R3:
```
configure terminal
int Serial1/0
ip address 10.0.0.1 255.255.255.0
encapsulation frame-relay
frame-relay intf-typ dte
frame-relay map ip 10.0.0.2 101 broadcast
no shutdown
end
```

#### R4:
```
configure terminal
int Serial1/0
ip address 10.0.0.2 255.255.255.0
encapsulation frame-relay
frame-relay intf-typ dte
frame-relay map ip 10.0.0.1 101 broadcast
no shutdown
end
```

Já a configuração dos switches Frame Relay é como segue:


### FRSW1:

![fr1.png](https://github.com/PudiMari/ATM-e-Frame-Relay/blob/main/FRSW1.png?raw=true)


### FRSW2:
![fr2.png](https://github.com/PudiMari/ATM-e-Frame-Relay/blob/main/FRSW2.png?raw=true)


### FRSW3:
![fr3.png](https://github.com/PudiMari/ATM-e-Frame-Relay/blob/main/FRSW3.png?raw=true)

## Pings

### Ping de R1 
![ping.png](https://github.com/PudiMari/ATM-e-Frame-Relay/blob/main/PingR1.png?raw=true)

### Ping de R2
![ping.png](https://github.com/PudiMari/ATM-e-Frame-Relay/blob/main/PingR2.png?raw=true)

### Ping de R3
![fr4.png](https://github.com/PudiMari/ATM-e-Frame-Relay/blob/main/PingR3.png?raw=true)

### Ping de R4
![fr4.png](https://github.com/PudiMari/ATM-e-Frame-Relay/blob/main/PingR4.png?raw=true)

### Ping de R5
![fr4.png](https://github.com/PudiMari/ATM-e-Frame-Relay/blob/main/PingR5.png?raw=true)
