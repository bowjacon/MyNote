## 1.1 SA组网和NSA组网

SA组网(非独立组网)是指使能5G网络不需要其他移动通信系统的辅助,可以独立进行工作。NSA组网(独立组网)是指使能5G网络需要其他移动通信系统的辅助,如果辅助缺失,那么5G网络不可以独立进行工作,通常而言5G网络建设阶段,NSA组网方式是在表明5G网络的使用需要4G网络进行辅助。



<table border="2" bordercolor="black" width="300" cellspacing="0" cellpadding="5">
    <tr>
        <td>组网类型</td>
        <td>部署流程</td>
    </tr>
    <tr>
        <td>NSA</td>
        <td>UE→4G基站/5G基站→4G/5G</td>
    </tr>
            <td>SA</td>
        <td>UE→5G基站→5G</td>
</table>



**SA组网options**

5G移动通信系统的接入网有两种接入方式:ng-eNB和gNB。3GPP确定的SA组网options分别为Option2和Option5,其中对应接入网使用gNB的为Option2；对应接入网使用ng-eNB的为Option5。



**NSA Option3系列(2017年12月制定)**

4G基站(eNB)和5G基站(gNB)共用4G核心网(EPC),LTE eNB和5G gNB用户面可以直接连接到EPC,控制面板仅经由LTE e NB连接到EPC。用户面可以分别经由LTE eNB、EPC或者gNB进行分流。优势在于不必新增5G核心网,利用运营商现有4G网络基础设施快速部署5G,抢占覆盖和热点。但是5G信令全走4G通道,有4G核心网络信令过载风险,因此该阶段主要解决初期的5G覆盖。Option3系列各类型的区别在于分流路径不同,其中Option3通过eLTE基站进行用户面分流,而Option3a和Option3x则分别通过EPC+和5G NR进行用户面分流。



1.option3:所有上行/下行数据流都通过LTE部分的基站(eNB)传输,eNB决定哪些数据转发给5G部分的基站(en-gNB)。简单来说en-gNB不直接与4G核心网通信。

2.option3A:LTE eNB和en-gNB都可以直接与EPC核心网通信,但它们不能通过X2接口直接相互通信(单方向通信)。这意味着一个数据承载不能再LTE和NR之间共享负载。

3.option3X:用户数据流直接流向5G部分的基站,然后通过无线方式传送到移动设备。数据的一部分也可以通过X2接口转发给LTE部分的基站,然后传输给UE。



**NSA Option7系列(2018年12月确定)**

增强4G基站(ng-eNB)与5G基站(gNB)共用5G核心网(EPC),该阶段5G核心网替代了4G核心网,控制面则仅由ng-eNB连接到5GC,用户面可以分别经由ng-eNB、5GC或者gNB进行分流,解决了4G核心网信令过载风险,主要面向5G容量需求。5G NR接入网做数据锚点支持X架构(LTE设备能力弱于NR,不适合做锚点)。Option7系列各类型的区别在于分流路径不同,Option7通过eLTE基站进行用户面分流,而Option7a和Option7x分别通过5GC和5G NR进行用户面分流。



1.Option7:所有的控制面信令都经由eNB转发,eNB将数据分流给gNB。

2.Option7A:所有的控制面信令都经由eNB转发,NGC将数据分流至gNB。

3.Option7X:所有的控制面信令都经由eNB转发,gNB可将数据分流至gNB。



**NSA Option4系列(2019年12月确定)**

增强型4G基站(ng-eNB)与5G基站(gNB)共用5G核心网(5GC),该阶段5G核心网替代了4G核心网,控制面则仅由5G gNB连接到5GC,用户面可以分别经由gNB、5GC或者ng-eNB进行分流。该阶段不仅面向5G的增强型移动带宽场景(eMBB),还面向大规模联网(mMTC)和低时延高可靠物联网(uRLLC)。是面向万物连接时代5G的多样化业务。Option4系列各类型的区别在于分流路径不同,Option4通过5G NR进行用户面分流,而Option4a则通过5GC进行用户面分流。



1.Option4:所有的控制面都经由gNB转发,gNB将数据分流给eNB。

2.Option4A:所有的控制面信令都经由gNB转发,NGC将数据分流至eNB。



<table border="2" bordercolor="black" width="300" cellspacing="0" cellpadding="5">
    <tr>
        <td>基站协议</td>
        <td>定义</td>
    </tr>
    <tr>
        <td>eNB</td>
        <td>面向终端提供E-UTRAN用户面和控制面协议,并且通过S1接口连接到EPC的网络节点</td>
    </tr>
    <tr>
    <td>ng-eNB</td>
        <td>面向终端提供E-TURAN用户面和控制面协议,并且通过NG接口连接到5GC的网络节点；</td>
    </tr>
    <tr>
    <td>gNB</td>
        <td>面向终端提供NR用户面和控制面协议,并且通过NG接口连接到5GC的网络节点</td>
    </tr>
    <tr>
    <td>en-gNB</td>
        <td>面向终端提供NR用户面和控制面协议,并且通过S1-U接口连接到EPC的网络节点</td>
    </tr>
</table>

<table border="2" bordercolor="black" width="300" cellspacing="0" cellpadding="5">
    <tr>
        <td>分类</td> 
        <td>非独立NR(NSA)架构</td>
        <td>独立NR(SA)架构</td>
    </tr>
    <tr>
        <td>支持功能/td>
        <td>仅支持eMBB</td>
        <td>全部5G功能</td>
    </tr>
    <tr>
    <td>LTE现网</td>
        <td>需要升级LTE基站以及核心网支持NSA</td>
<td>不影响现网LTE</td>
    </tr>
    <tr>
    <td>终端</td>
        <td>5G NR下需要提供Customized 4G NAS UE with 5G RRC,eLTE理论支持LTE终端</td>
       <td>5G NR下使用5G UE LTE终端继续使用在LTE网络下</td>
    </tr>
    <tr>
<td>5G新频NR以及天线</td>
        <td>全部新加,不管高低频</td>
        <td>全部新加,不管高低频</td>
    </tr>
    <tr>
    <td>核心网</td>
        <td>初期只需要升级网EPC后期可以选择新建5G核心网支持eLTE</td>
        <td>新加5G核心网</td>
    </tr>
    <tr>
    <td>初期成本</td>
        <td>低</td>
        <td>高</td>
    </tr>
    <tr>
    <td>后期维护成本</td>
        <td>高(升级软件需要升级LTE基站)</td>
        <td>低</td>
    </tr>
    <tr>
    <td>组网</td>
        <td>复杂(需要考虑到LTE的链路)</td>
        <td>简单</td>
    </tr>
    <tr>
    <td>lOT对接</td>
        <td>不需要5G NR接入与核心网跨异厂家lOT测试,LTE或eLTE升级后的EPC lOT需要对接验证</td>
        <td>需要5G NR与5G核心网跨异厂家lOT测试成熟</td>
    </tr>
    <tr>
    <td>演进</td>
        <td>可以通过升级与网络调整变成SA</td>
        <td>SA是最终模式</td>
    </tr>
</table>





## 2.1 MR-DC技术

MR-DC(Multi-RAT Dual Connectivity,多接入网技术双连接)是指一部终端可以同时连接4G网络和5G网络,同时使用两个网络进行业务,此时终端需要具备至少两个MAC实体,支持双发双收。对应不同的网络结构,双连接有不同的名称。



<table border="2" bordercolor="black" width="300" cellspacing="0" cellpadding="5">
    <tr>
        <td>核心网</td>
        <td>主节点</td>
        <td>辅节点</td>
        <td>名称</td>
    </tr>
    <tr>
        <td rowspan="2">EPC</td>
        <td colspan="2">E-UTRA</td>
        <td>DC</td>
    </tr>
    <tr>
        <td>E-UTRA</td>
        <td>NR</td>
        <td>EN-DC</td>
    </tr>
    <tr>
        <td rowspan="3">5GC</td>
        <td>NG-RAN E-UTRA</td>
        <td>NR</td>
        <td>NGEN-DC</td>
    </tr>
    <tr>
        <td>NR</td>
        <td>E-UTRA</td>
        <td>NE-DC</td>
    </tr>
    <tr>
        <td colspan="2">NR</td>
        <td>NR-DC</td>
    </tr>
</table>

以option3x组网场景为例,从控制面来看L网络侧MN(eNB)和终端之间会建立面向核心网的控制平面连接,维护惟一的RRC状态。MN(eNB)和SN(gNB)具有各自的RRC实体,可以生成要发送到终端的RRC PDU。



DC与CA(Carrier Aggregation,载波聚合)是一对极易混合的概念。3GPP在R10版本引入CA这一概念。CA技术中终端也会与多个接入网网元建立连接,但是控制面板连接仅有一个。



<table border="2" bordercolor="black" width="300" cellspacing="0" cellpadding="5">
    <tr>
    <td>项目</td>
        <td>MR-DC</td>
        <td>CA</td>
    </tr>
    <tr>
    <td>本质</td>
        <td>聚合协议层是PDCP层,时延宽松；</td>
        <td>聚合协议层是MAC层,对时延要求严格</td>
    </tr>
    <tr>
    <td>实现</td>
        <td>异系统或同系统的不同基站资源</td>
        <td>多为同系统,异系统实现复杂</td>
    </tr>
    <tr>
<td>机制</td>
        <td>不同节点使用不同的TA(Time Advance,时间提前量)做时间同步；每个终端的主节点配置固定；上下行节点数相同</td>
        <td>资源不够的情况下,才考虑添加CC；不同小区共用TA；每个终端的主小区配置可以不同；上下行可以聚合不同载波</td>
    </tr>
    <tr>
    <td>对终端</td>
        <td>两个MAC实体(控制面协议栈)；</td>
        <td>一个MAC实体,支持CA；</td>
    </tr>
</table>



## 3.1 CU/DU组网部署

**NR的不同网络结构**

根据不同的业务和部署场景,NR架构总体可以分为CU和DU两级,但是实际部署可以出现CU、DU和AAU分离的三级配置,也可以出现AAU直接连入中心结点。



**组网部署-eMBB**

为了支持eMBB业务的覆盖和容量需求,CU和DU需要进行分离部署,分为两种形式:Macro(宏)方式和Micro(微)方式。



**组网部署-mMTC**

对于面向垂直行业的机器通信业务,在建设5G网络时,需要考虑机器通信的特点。大规模机器通信普遍对时延要求较低,其特点有两个:数据量少而且站点稀疏；站点数量多,且分布密集。



**DU资源池组网部署**

当业务容量需要变高,在密集部署情况下,基于理想前传条件,多个DU可以联合部署,形成基带池,提高基站资源池的利用率,并且可以利用多小区协作传输和协作处理以提高网络的覆盖和容量。



**高时延和低时延部署**

语音业务对带宽和时延要求不高,此时DU可以部署在基站侧；对于大带宽低时延业务(比如视频或者虚拟现实),一般需要高速传输网络或者光纤直接连接中心机房,并在中心机房部署缓存服务器,以降低时延并提示用户体验。