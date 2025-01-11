# The OSI Model

The goal in defining the **ISO/OSI** standard was to create a reference model that enables the communication of different technical systems via various devices and technologies and provides compatibility. The **OSI** model uses **seven** different layers, which are hierarchically based on each other to achieve this goal. These layers represent phases in the establishment of each connection through which the sent packets pass. In this way, the standard was created to trace how a connection is structured and established visually.

![image](https://github.com/user-attachments/assets/7d69710d-9f4e-428e-b962-769636c02578)

The layers **2-4** are **transport oriented**, and the layers **5-7** are **application oriented** layers. In each layer, precisely defined tasks are performed, and the interfaces to the neighboring layers are precisely described. Each layer offers services for use to the layer directly above it. To make these services available, the layer uses the services of the layer below it and performs the tasks of its layer.

If two systems communicate, all seven layers of the **OSI** model are run through at least **twice**, since both the sender and the receiver must take the layer model into account. Therefore, a large number of different tasks must be performed in the individual layers to ensure the communication's security, reliability, and performance.

When an application sends a packet to the other system, the system works the layers shown above from layer **7** down to layer **1**, and the receiving system unpacks the received packet from layer **1** up to layer **7**.

![image](https://github.com/user-attachments/assets/c309b73e-ef42-403a-822b-240e381fd93a)

