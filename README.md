**欢迎你来到这个仓库，这个仓库记录了我个人学习各个方向的一些经验。涉及程序设计、电控、嵌入式、传统视觉，方便各位迈出第一步。**

**这只是个Guide，因此这里只提供一些路线并记录出现的问题，如果你也出现了这个问题，希望能够帮到你❤。**

![Alt text](Ver0.1.png)
``` mermaid
flowchart LR
subgraph 新手村
    direction TB
    A(C语言基础
    部分算法基础)

    B(硬件科普
    电子电路基础)
    A o--o B
end
subgraph 进阶
direction TB
    K(嵌入式系统)
    
    C(OpenCV功能理解与应用
    了解机器学习的相关方法
    了解深度学习常用模型
    )

    D(学习理解嵌入式C语言
    32位MCU外设原理与应用)

    E(学习常用电子元器件-阻容感等元件
    MCU外围电路设计、电源电路、常用外设模块
    原理图、PCB设计与调试)
    
    M(控制算法)

    F(常用通信协议IIC、UART、SPI、CAN、RS232……)

    J(熟练使用Linux系统发行版
    推荐Ubuntu 20.04)

    L(在至少一款Linux开发板上
    部署环境与工程)
end

subgraph 视觉
    G(深度学习
    神经网络
    图像处理)
end
subgraph 嵌入式
direction TB
subgraph 嵌入式软件
    H(MCU外设应用
    嵌入式UI设计
    人机交互
    在硬件平台上实现需求)
end
subgraph 电控
    I(硬件电路设计
    PCB制板与调试
    电控机械臂等制作与调试)
end
end
    新手村-->C & D & E & F & K & J & L & M

    C --⭐⭐⭐⭐⭐-->   视觉
    J --⭐⭐⭐-->   视觉
    L --⭐⭐⭐⭐-->   视觉

    D --⭐⭐⭐⭐⭐--> 嵌入式软件
    E --⭐⭐--> 嵌入式软件
    F --⭐⭐⭐⭐--> 嵌入式软件
    K --⭐⭐⭐--> 嵌入式软件

    D --⭐⭐⭐⭐--> 电控
    E --⭐⭐⭐⭐--> 电控
    F --⭐⭐--> 电控
    M --⭐⭐⭐⭐⭐--> 电控
```

<div style="text-align: right;">Ver 0.1 : 2023年10月29日 孙琪轩</div>
