## 1.1 5G接口系统功能与协议

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



Xn接口是NG-RAN之间的接口。在CU\DU分离的情况下,Xn-C是CU-C之间的接口,Xn-U是CU-U之间的接口。