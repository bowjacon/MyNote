## 1.1 5G移动通信系统

$$
系统整体架构
\begin{cases}
5GC(5G核心网)\\
NG-RAN(5G无线接入网):gNB、ng-eNB
\end{cases}
$$

其中5GC与NG-RAN之间通过NG接口连接；而NG-RAN内部通过Xn接口连接



## 1.2 4G移动通信系统

$$
系统整体架构
\begin{cases}
EPC(演进分组核心网)\\
E-UTRAN(演进通用陆地无线接入网络):eNB
\end{cases}
$$

其中EPC与E-UTRAN之间通过S1接口连接；而E-UTRAN内部通过X2接口连接。

5G和4G中都提到了RAN,意为“无线接入网络”。相比于4G而言,5G在RAN中引入了CU(集中单元)、以及DU(分布单元),其关键技术为MEC(多接入边缘技术)。



## 2.1 5G网络架构演进趋势

1.实现从“互联网应用被动适应网络”“网络主动、快速、灵活适应互联网应用”。

2.网络和资源的部署将打破行政管理体制恶魂传统组网思路的制约,转向以IDC为核心的新格局。

模拟通信→数字通信→互联网→SDN/NFV、



## 2.2 5G移动网络通信整体网络架构

5G网络功能之间的信息交互可以基于两种方式表示,其一为基于服务表示；其而为基于点对点表示,实际部署时,也可以采用两种方式相结合的表示方式,因为并不是所有的接口都适合于基于服务表示,对于有些接口点对点表示方式更加适合。

5G无线接入网的基站网元功能拆分为CU和DU。更多协议栈功能位于CU,集中化程度增加。PDCP上移便于形成数据锚点,便于支持用户面的双连接/多连接。

<table border="2" bordercolor="black" width="300" cellspacing="0" cellpadding="5">
    <tr>
        <td >切换方案</td>
        <td >资源集中度</td>
        <td >协同性能</td>
        <td >传输带宽要求</td>
        <td >传输时延要求</td>
    </tr>
    <tr>
        <td >option1</td>
        <td >RRC</td>
        <td rowspan="3">
            不支持
        </td>
        <td rowspan="5">
            低
        </td>
        <td rowspan="3">
            宽松
        </td>
    </tr>
    <tr>
        <td >option2</td>
        <td rowspan="3">RRC+L2(部分)</td>
    </tr>
    <tr>
        <td>option3</td>
    </tr>
    <tr>
        <td>option5</td>
        <td >集中化调度</td>
        <td >较严</td>
    </tr>
    <tr>
        <td>option6</td>
        <td>RRC+L2</td>
        <td>集中化调度、多小区干扰协调</td>
        <td rowspan="3">严格</td>
    </tr>
    <tr>
        <td>option7</td>
        <td>RRC+L2+PHY(部分)</td>
        <td  rowspan="2">集中化调度、多小区干扰协调上行高级接收机</td>
        <td>中</td>
    </tr>
    <tr>
        <td>option8</td>
        <td>RRC+L2+PHY</td>
        <td>高</td>
    </tr>
</table>


## 2.3 5G主要网元功能

5G系统主要由接入网(AN)和核心网(5G)组成,AN与5GC的主要功能如下。

**gNB或ng-eNB**

-小区间无线资源管理

-无线承载控制

-连接移动性管理

-无线接入控制

-测量配置与下发

-动态资源分配

**AMF**

-NAS安全

-空闲状态移动性管理

**UPF**

-移动性能点

-PDU处理

**SMF**

-UE IP地址分配

-PDU会话控制
