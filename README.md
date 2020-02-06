# Incremental-Encoder
Incremental encoders are often used for industrial applications like robotics or positioning tracking. Encoders for industrial applications comes mostly with a differential RS422 interface. The RS422 is only used als hardware layer. No serial protocol will be transmitted over the RS422. Only the pulses of the encoder itself are directely transfered via 3 different RS422 channels: SIN, COS and Z (zero position).

![My image](https://hackster.imgix.net/uploads/attachments/1067763/img_20200206_102637_xY8ei5e82d.jpg?auto=compress%2Cformat&w=680&h=510&fit=max)

I will show in this small project how to use an industrial incremental encoder - in our case SICK DFS60 - with an Arduino UNO. 


## Hardware

[Arduino UNO](https://store.arduino.cc/)

[Arduino RS422 shield](https://www.hwhardsoft.de/english/projects/rs485-arduino/)

[Encoder Sick DFS60](https://www.sick.com/de/en/encoders/incremental-encoders/dfs60/c/g244428)


## dip switch setting of RS422 shields

The dip switch setting for any shield is the same:
    
    S1: ON, OFF, OFF, OFF
    
    S2: OFF, OFF, ON, ON
    
    S3: ON, OFF, OFF, OFF
    


## dip switch setting of RS422 shields

The Jumper setting for any shield is different. Depending from the connected channel the RX pin is configured to:
    
    shield for Z channel: D2
    
    shield for COS channel: D3
    
    shield for SIN channel: D4
    

The voltage jumper JP1 must be setted to 5V.


## Wiring

![My image](https://github.com/HWHardsoft/Incremental-Encoder/blob/master/wiring/wiring_DFS60.jpg)

Because of the 3 independent RS422 channels we need 3 RS422 inputs for the Arduino. For this purpose I've used 3 pcs of my Arduino RS422/RS485 shields - stacked on one Arduino: 


![My image](https://hackster.imgix.net/uploads/attachments/1067753/img_20200206_110349_ZckkQ70oLG.jpg?auto=compress%2Cformat&w=680&h=510&fit=max)


## License

This library is free software; you can redistribute it and/or modify it under the terms of the GNU Lesser General Public License as published by the Free Software Foundation; either version 2.1 of the License, or (at your option) any later version.

This library is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU Lesser General Public License for more details.

You should have received a copy of the GNU Lesser General Public License along with this library; if not, write to the Free Software Foundation, Inc., 51 Franklin St, Fifth Floor, Boston, MA 02110-1301 USA
