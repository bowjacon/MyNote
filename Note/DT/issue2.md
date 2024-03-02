## 1.1 NG接口系统功能

NG接口是NG-RAN和5G核心网之间的接口,支持控制面和用户面分离,支持模式化设计

<table border="2" bordercolor="black" width="300" cellspacing="0" cellpadding="5">
    <tr>
        <td>NG-C接口功能与流程</td>
        <td>具体描述</td>
    </tr>
    <tr>
        <td rowspan="2">PDU会话管理过程</td>
        <td>完成PDU会话的NG-RAN资源建立,释放或修改过程</td>
    </tr>
    <tr>
        <td>PDU会话资源建立、PDU会话资源修改、PDU会话资源释放、PDU会话资源通告、PDU会话资源修改指示</td>
    </tr>
    <tr>
        <td rowspan="2">UE上下文管理过程</td>
        <td>完成UE上下文建立,释放或修改过程；</td>
    </tr>
    <tr>
        <td>初始上下文建立、UE上下文修改、UE上下文释放请求、UE上下文释放</td>
    </tr>
    <tr>
        <td rowspan="2">NAS发送过程</td>
        <td>完成AMF和UE之间的NAS信令数据透传过程；</td>
    </tr>
    <tr>
        <td>初始化UE消息(NG-RAN node发起)、上行NAS传输(NG-RAN node发起)、下行NAS传输(AMF发起)、NAS无法传输指示(NG-RAN node发起)、重新路由NAS请求(AMF发起)</td>
    </tr>
    <tr>
        <td rowspan="2">UE移动管理过程</td>
        <td>完成UE移动切换的准备,执行或取消过程</td>
    </tr>
    <tr>
        <td>切换准备、切换资源分配、切换通知、路径切换请求、上下行RAN状态转发、切换取消</td>
    </tr>
    <tr>
        <td>寻呼过程</td>
        <td>完成寻呼区域内向NG-RAN节点发送寻呼请求过程</td>
    </tr>
    <tr>
        <td rowspan="2">AMF管理过程</td>
        <td>完成AMF告知NG-RAN节点AMF状态和去激活与指定UE NGAP UE组合过程</td>
    </tr>
    <tr>
        <td>AMF状态指示、NGAP组合去激活(FFS)</td>
    </tr>
    <tr>
        <td rowspan="2">NG接口管理</td>
        <td>完成NG接口管理过程</td>
    </tr>
    <tr>
    <td>NG建立、NG重置、RAN配置更新、AMF配置更新、错误提示</td>
    </tr>
</table>


**NG-U接口主要功能**

1.NG-U接口在NG-RAN节点和UPF之间提供非保证的用户平面PDU传送；

2.协议栈传输网络层建立在IP传输上；

3.GTP-U在UDP/IP之上用于承载NG-RAN节点和UPF之间的用户面PDU



## 1.2 Xn接口系统功能

Xn接口是NG-RAN之间的接口。在CU\DU分离的情况下,Xn-C是CU-C之间的接口,Xn-U是CU-U之间的接口。
<table border="2" bordercolor="black" width="300" cellspacing="0" cellpadding="5">
    <tr>
        <td>功能</td>
        <td>具体功能</td>
        <td>功能描述</td>
    </tr>
    <tr>
        <td rowspan="5">Xn-C接口管理和差错处理功能</td>
        <td>Xn建立功能</td>
        <td>允许两个NG-RAN nodes间Xn接口的初始建立,包括应用层数据交互。</td>
    </tr>
    <tr>
        <td>差错指示功能</td>
        <td>允许应用层上一般错误情况上报</td>
    </tr>
    <tr>
        <td>Xn重置功能</td> 
        <td>允许NG-RAN node告知另一个NG-RAN node其已经从非正常失败状态恢复,第二个node内需要删除与第一个node相关的所有上下文(应用层数据除外)并释放伴生资源</td>
    </tr>
    <tr>
        <td>Xn配置数据更新功能</td>
        <td>允许两个NG-RAN node随时更新应用数据</td>
    </tr>
    <tr>
        <td>Xn移除功能</td>
        <td>允许两个NG-RAN nodes删除各自的Xn接口</td>
    </tr>
    <tr>
        <td rowspan="5">UE移动管理功能</td>
        <td>切换准备功能</td>
        <td>允许源和目的NG-RAN node间的信息交互从而完成给定UE到目的NG-RAN node初始切换</td>
    </tr>
    <tr>
        <td>切换取消功能</td>
        <td>允许通知已准备好的目的NG-RAN node准备的切换不进行,同时释放切换准备期间的资源分配</td>
    </tr>
    <tr>
        <td>恢复UE上下文功能</td>
        <td>允许NG-RAN node从其他node恢复UE上下文</td>
    </tr>
    <tr>
        <td>RAN寻呼功能</td>
        <td>允许NG-RAN node初始化非激活态UE的寻呼功能</td>
    </tr>
    <tr>
        <td>数据转发控制功能</td>
        <td>允许源和目的NG-RAN nodes间用于数据转发传输承载的建立和释放</td>
    </tr>
    <tr>
        <td>双连接功能</td>
        <td colspan="2">使能NG-RAN中辅助节点内额外资源的使用</td>
    </tr>
</table>





**Xn-U接口主要功能**

1.Xn-U接口提供用户平面PDU的非保证传送,并支持分离Xn接口为无线网络功能的传输网络功能,以促进未来技术的引用；

2.数据转发功能,允许NG-RAN节点间数据转发从而支持双连接和移动性操作；

3.流控制功能,允许NG-RAN节点接收第二个节点用户面数据从而提供数据流相关的反馈信息。



CU\DU分离场景下,E1接口是指CU-C与CU-C之间的接口,E1接口只有控制面接口(E1-C接口)。E1接口是开放接口,支持端口之间指令信息的交换,支持5G系统服务和新功能。E1-C接口不能用于用户数据转发。



## 1.3 E1接口系统功能

**1.E1接口管理功能**

-错误指示(gNB-CU-UP或者gNB-CU-CP或者gNB-CU-CP发出错误指示);

-复位功能用于gNB-CU-UP与gNB-CU-CP建立之后和发生故障事件之后初始化对等实体；

-gNB-CU-UP与gNB-CU-CP之间应用层数据的互操作；

-gNB-CU-UP配置更新：gNB-CU-UP将NR CGI、s-nssai、PLMB-ID和gBNB-CU-UP支持的Qos信息通知给gNB-CU-CP；

**2.E1上下文管理功能**

-上下文承载建立(gNB-CU-CP)；

-上下文承载修改与释放(可以由gNB-CU或gNB-DU发起)；

-Qos流映射(gNB-CU执行)；

-下行数据通知(gNB-CU-UP发起)；

-承载不活动通知；

**3.TE ID分配功能(gNB-CU-UP发起)**

-F1-U UL GTP TEID、S1-U DL GTP TEID、NG-U DL GTP TEID X2-U DL/UL FTO TEUD、Xn-U DL/UL GTP TEID；



CU\DU分离场景下、F1接口是指CU与DU之间的接口,区分为用户面接口(F1-U接口)和控制面接口(F1-C接口)。F1接口支持eNB-point之间的信令交互,包括支持不同eNB-point的数据发送。



## 1.4 F1接口系统功能

**1.F1接口管理功能**

-错误提示；

-复位功能用于在节点建立之后和发生故障事件之后初始化对等实体；

**2.系统信息管理功能**

-系统广播信息的调度在gNB-DU中执行,gNB-DU负责NR-MIB、SIB1的编码,gNB-CU负责其他SI消息的编码；

**3.F1 UE上下文管理功能**

-基于接纳控制准则、由gNB-CU发起并由gNB-DU接收或拒绝F1 UE上下文的建立；

UE上下文的修改(可以由gNB-CU或gNB-DU发起)；

-QoS流和无线承载之间的映射(gNB-CU执行)；

-管理建立、修改和释放DRB和SRB资源(DRB资源的建立和修改由gNB-CU触发)；

**4.RRC消息传送功能**

-RRC消息通过F1-C传送,gNB-CU负责用gNB-DU提供的辅助信息对专用RRC消息进行编码



**F1-U接口主要功能**

1.用户数据传输；

2.CU和DU之间传输用户数据；

3.流量控制功能；

4.控制下行用户数据流向DU。



## 2.1 控制面协议栈

NAS层是控制面功能,位于核心网的AMF与终端之间,功能包括核心网承载管理、注册管理、连接管理、会话管理、鉴权、安全性和策略控制。



**控制面的主要功能**

1.RLC和MAC层功能与用户名中的功能一致

2.PDCP层完成加密和完整性保护

3.RRC层完成广播,寻呼,RRC连接管理,资源控制移动性管理,UE测量报告控制

4.NAS层完成核心网承载管理,鉴权及安全控制



## 2.2用户名协议栈

**用户面的主要功能**

1.头压缩,加密,调度,ARQ\HARQ

2.5G用户面增加的新的协议层SDAP,完成流(5G QoS flow)到无线承载(DRB)的QoS映射,为每个报文打上流标识(QFI: QoS flow ID)







