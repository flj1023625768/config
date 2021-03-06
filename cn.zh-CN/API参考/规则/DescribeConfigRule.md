# DescribeConfigRule

调用DescribeConfigRule接口查询规则详情。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Config&api=DescribeConfigRule&type=RPC&version=2019-01-08)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeConfigRule|要执行的操作，取值：DescribeConfigRule。 |
|ConfigRuleId|String|是|cr-2a914fcf617e00c9\*\*\*\*|规则ID。如果查询某个成员账号下的规则，则需要设置MultiAccount为true，设置MemberId为成员账号ID。 |
|MultiAccount|Boolean|否|false|企业管理账号是否查询成员账号的规则详情。取值：

 -   true：是。企业管理账号查询资源目录中所有成员账号的规则详情。
-   false（默认值）：否。企业管理账号查询当前账号的规则详情。

 **说明：** 当您使用个人版配置审计时，请忽略该参数。 |
|MemberId|Long|否|123456789|待查询规则归属的成员账号ID。默认为空。当MultiAccount设置为true时，该参数有效。

 -   当MemberId为空时，查询企业管理账号和所有成员账号的指定规则详情。
-   当MemberId不为空时，查询指定成员账号的指定规则详情。

 **说明：** 当您使用个人版配置审计时，请忽略该参数。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|ConfigRule|Struct| |规则信息。 |
|ConfigRuleArn|String|acs:config::120886317863\*\*\*\*:config-rule/cr-e4b06457e0d900df\*\*\*\*|规则的ARN。 |
|ConfigRuleEvaluationStatus|Struct| |资源的评估状态。 |
|FirstActivatedTimestamp|Long|1586422960385|首次激活时间戳。 |
|FirstEvaluationStarted|Boolean|true|规则是否已执行过评估。取值：

 -   true（默认值）
-   false |
|LastErrorCode|String|FunctionNotFound|规则最近一次执行的错误码。 |
|LastErrorMessage|String|function 'funtionName' does not exist in service 'serviceName'|规则最近一次执行的错误信息。 |
|LastFailedEvaluationTimestamp|Long|1574996580279|规则最近一次异常评估的时间戳。 |
|LastFailedInvocationTimestamp|Long|1574996580301|规则最近一次异常调用的时间戳。 |
|LastSuccessfulEvaluationTimestamp|Long|1586423432010|规则最近一次成功评估的时间戳。 |
|LastSuccessfulInvocationTimestamp|Long|1586423432352|规则最近一次成功调用的时间戳。 |
|ConfigRuleId|String|cr-2a914fcf617e00c9\*\*\*\*|规则ID。 |
|ConfigRuleName|String|rds-cpu-min-count-limit-rd|规则名称。 |
|ConfigRuleState|String|ACTIVE|当前规则的运行状态。取值：

 -   ACTIVE：应用中
-   EVALUATING：评估中
-   INACTIVE：已停用 |
|CreateBy|Struct| |规则的创建信息。 |
|ConfigRuleSceneId|String|level3\_protection|创建规则的场景ID。

 **说明：** 当CreatorType为CONFIG\_RULE\_SCENE时，该参数不为空。 |
|ConfigRuleSceneName|String|等保预检|创建规则的场景名称。

 **说明：** 当CreatorType为CONFIG\_RULE\_SCENE时，该参数不为空。 |
|CreatorId|String|level3\_protection|创建者ID。

 **说明：** 当CreatorType为CONFIG\_RULE\_SCENE时，该参数不为空。 |
|CreatorName|String|等保预检|创建者名称。

 **说明：** 当CreatorType为CONFIG\_RULE\_SCENE时，该参数不为空。 |
|CreatorType|String|CONFIG\_RULE\_SCENE|创建者类型。取值：

 -   RESOURCE\_DIRECTORY：当您使用企业版配置审计时，由企业管理账号创建规则。
-   CONFIG\_RULE\_SCENE：当您使用个人版配置审计时，系统自动创建某些应用场景，例如：等保预检、OSS合规基线、CIS合规检测。 |
|CreateTimestamp|Long|1586423432010|创建规则时的时间戳。 |
|Description|String|您账号下的RDS实例CPU数量大于等于您设置的阈值，视为“合规”。|规则的描述信息。 |
|InputParameters|Map|\{"cpuCount": "2" \}|规则入参。 |
|ManagedRule|Struct| |托管规则详情。 |
|CompulsoryInputParameterDetails|Map|\{"cpuCount":\{"type":"integer","defaultValue":"2"\}\}|托管规则必填参数的信息。 |
|Description|String|您账号下的RDS实例CPU数量大于等于您设置的阈值，视为“合规”。|托管规则的描述信息。 |
|Identifier|String|rds-cpu-min-count-limit|托管规则的标识符。 |
|Labels|List|\["RDS","CPU"\]|托管规则的标签列表。 |
|ManagedRuleName|String|rds-cpu-min-count-limit|托管规则的名称。 |
|OptionalInputParameterDetails|Map|\{"tag1Value":\{"type":"string","defaultValue":""\},"tag2Key":\{"type":"string","defaultValue":""\}\}|托管规则可选参数的描述。 |
|SourceDetails|Array of SourceDetails| |托管规则详情。 |
|EventSource|String|aliyun.config|规则的事件来源。

 **说明：** 目前仅支持配置审计事件：aliyun.config。 |
|MaximumExecutionFrequency|String|Six\_Hours|规则的执行周期。取值：

 -   One\_Hour：1小时
-   Three\_Hours：3小时
-   Six\_Hours：6小时
-   Twelve\_Hours：12小时
-   TwentyFour\_Hours：24小时 |
|MessageType|String|ConfigurationItemChangeNotification|规则的触发机制。取值：

 -   ConfigurationItemChangeNotification：配置变更
-   ScheduledNotification：周期执行 |
|MaximumExecutionFrequency|String|Six\_Hours|规则的执行周期。取值：

 -   One\_Hour：1小时
-   Three\_Hours：3小时
-   Six\_Hours：6小时
-   Twelve\_Hours：12小时
-   TwentyFour\_Hours：24小时 |
|ModifiedTimestamp|Long|1586423432010|规则最近一次修改的时间戳。 |
|RiskLevel|Integer|1|规则的风险等级。取值：

 -   1：高风险
-   2：中风险
-   3：低风险 |
|Scope|Struct| |规则的监控范围。 |
|ComplianceResourceId|String|vpc-6weoy5flv41pj4wvr\*\*\*\*|待评估资源ID。

 **说明：** 如果该参数为空，则适用于指定资源类型的全部资源。 |
|ComplianceResourceTypes|List|\["ACS::RDS::DBInstance"\]|待评估资源类型列表。 |
|Source|Struct| |规则执行逻辑的来源信息。 |
|Identifier|String|rds-cpu-min-count-limit|规则引用的规则函数标识。

 -   如果规则使用了托管规则，则该参数为托管规则名称。
-   如果规则使用了自定义函数，则该参数为函数ARN。 |
|Owner|String|ALIYUN|规则来源的归属。取值：

 -   CUSTOM\_FC：用户自定义函数
-   ALIYUN：托管规则 |
|SourceConditions|Array of SourceConditions| |规则的配置条件。

 **说明：** 该参数仅适用于通过可视化编辑器创建的规则。 |
|DesiredValue|String|1|规则入参的期望值。 |
|Name|String|status|规则入参的名称。 |
|Operator|String|Equals|规则入参的操作符。通过SelectPath获取到的不同数据类型，对应不同的操作符。

 -   当数据类型为String时，取值：
    -   StringEquals：等于
    -   NotStringEquals：不等于
    -   StringIn：存在
    -   NotStringIn：不存在
    -   StringContains：包含
    -   NotStringContains：不包含
-   当数据类型为Number时，取值：
    -   Equals：等于
    -   NotEquals：不等于
    -   Less：小于
    -   LessOrEquals：小于等于
    -   Greater：大于
    -   GreaterOrEquals：大于等于
-   当数据类型为基于Base64进制编码的Base64 String时，取值：
    -   Base64Contains：包含
    -   NotBase64Contains：不包含
    -   Base64ContainsAll：包含全部
    -   Base64ExcludeAll：排除全部
-   当数据类型为Array时，取值：
    -   Contains：包含
    -   NotContains：不包含
    -   In：存在
    -   NotIn：不存在
    -   ContainsAll：包含全部
    -   ExcludeAll：排除全部
    -   IsEmpty：为空 |
|Tips|String|实例的状态|参数的提示信息。 |
|SourceDetails|Array of SourceDetails| |规则来源详情。 |
|EventSource|String|aliyun.config|事件来源。

 **说明：** 目前仅支持配置审计事件：aliyun.config。 |
|MaximumExecutionFrequency|String|Six\_Hours|规则的执行周期。取值：

 -   One\_Hour：1小时
-   Three\_Hours：3小时
-   Six\_Hours：6小时
-   Twelve\_Hours：12小时
-   TwentyFour\_Hours：24小时 |
|MessageType|String|ScheduledNotification|规则的触发机制。取值：

 -   ConfigurationItemChangeNotification：配置变更
-   ScheduledNotification：周期执行 |
|RequestId|String|A7A0FFF8-0B44-40C6-8BBF-3A185EFDF3D0|请求ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeConfigRule
&ConfigRuleId=cr-2a914fcf617e00c9****
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeConfigRuleResponse>
	  <RequestId>F63DFAFD-CE84-495D-A800-9E94B22C2346</RequestId>
	  <ConfigRule>
		    <ManagedRule>
			      <ManagedRuleName>rds-desired-instance-type</ManagedRuleName>
			      <Description>您账号下所有的RDS实例类型均已在阈值中列举出，视为“合规”。</Description>
			      <Identifier>rds-desired-instance-type</Identifier>
			      <CompulsoryInputParameterDetails>
				        <instanceTypes>
					          <defaultValue>rds.mysql.s2.large</defaultValue>
					          <description>实例类型</description>
					          <type>string</type>
				        </instanceTypes>
			      </CompulsoryInputParameterDetails>
			      <Labels>RDS</Labels>
			      <SourceDetails>
				        <EventSource>aliyun.config</EventSource>
				        <MessageType>ConfigurationItemChangeNotification</MessageType>
			      </SourceDetails>
			      <HelpUrl>https://help.aliyun.com/document_detail/147676.html#title-rt6-m9w-a52</HelpUrl>
		    </ManagedRule>
		    <Description>This rule is evaluated to compliant if all types of ApsaraDB RDS instances are included in the parameter value.</Description>
		    <ConfigRuleEvaluationStatus>
			      <FirstActivatedTimestamp>1602818958115</FirstActivatedTimestamp>
			      <LastSuccessfulEvaluationTimestamp>1602818964884</LastSuccessfulEvaluationTimestamp>
			      <FirstEvaluationStarted>false</FirstEvaluationStarted>
		    </ConfigRuleEvaluationStatus>
		    <ConfigRuleState>ACTIVE</ConfigRuleState>
		    <Source>
			      <Owner>ALIYUN</Owner>
			      <Identifier>rds-desired-instance-type</Identifier>
			      <SourceConditions>
				        <Operator>In</Operator>
				        <DesiredValue>rds.mysql.s2.large</DesiredValue>
				        <Required>true</Required>
				        <SelectPath>$.DBInstanceClass</SelectPath>
			      </SourceConditions>
			      <SourceDetails>
				        <EventSource>aliyun.config</EventSource>
				        <MessageType>ConfigurationItemChangeNotification</MessageType>
			      </SourceDetails>
		    </Source>
		    <ConfigRuleId>cr-138e6457e0d90072cc14</ConfigRuleId>
		    <Scope>
			      <ComplianceResourceTypes>ACS::RDS::DBInstance</ComplianceResourceTypes>
		    </Scope>
		    <ConfigRuleArn>acs:config::1208863178612953:config-rule/cr-138e6457e0d90072cc14</ConfigRuleArn>
		    <ConfigRuleName>rds-desired-instance-type</ConfigRuleName>
		    <RiskLevel>1</RiskLevel>
		    <InputParameters>
			      <instanceTypes>rds.mysql.s2.large</instanceTypes>
		    </InputParameters>
	  </ConfigRule>
</DescribeConfigRuleResponse>
```

`JSON` 格式

```
{
	"RequestId": "F63DFAFD-CE84-495D-A800-9E94B22C2346",
	"ConfigRule": {
		"ManagedRule": {
			"ManagedRuleName": "rds-desired-instance-type",
			"Description": "您账号下所有的RDS实例类型均已在阈值中列举出，视为“合规”。",
			"Identifier": "rds-desired-instance-type",
			"CompulsoryInputParameterDetails": {
				"instanceTypes": {
					"defaultValue": "rds.mysql.s2.large",
					"description": "实例类型",
					"type": "string"
				}
			},
			"Labels": [
				"RDS"
			],
			"SourceDetails": [
				{
					"EventSource": "aliyun.config",
					"MessageType": "ConfigurationItemChangeNotification"
				}
			],
			"HelpUrl": "https://help.aliyun.com/document_detail/147676.html#title-rt6-m9w-a52"
		},
		"Description": "This rule is evaluated to compliant if all types of ApsaraDB RDS instances are included in the parameter value.",
		"ConfigRuleEvaluationStatus": {
			"FirstActivatedTimestamp": 1602818958115,
			"LastSuccessfulEvaluationTimestamp": 1602818964884,
			"FirstEvaluationStarted": false
		},
		"ConfigRuleState": "ACTIVE",
		"Source": {
			"Owner": "ALIYUN",
			"Identifier": "rds-desired-instance-type",
			"SourceConditions": [
				{
					"Operator": "In",
					"DesiredValue": "rds.mysql.s2.large",
					"Required": true,
					"SelectPath": "$.DBInstanceClass"
				}
			],
			"SourceDetails": [
				{
					"EventSource": "aliyun.config",
					"MessageType": "ConfigurationItemChangeNotification"
				}
			]
		},
		"ConfigRuleId": "cr-138e6457e0d90072cc14",
		"Scope": {
			"ComplianceResourceTypes": [
				"ACS::RDS::DBInstance"
			]
		},
		"ConfigRuleArn": "acs:config::1208863178612953:config-rule/cr-138e6457e0d90072cc14",
		"ConfigRuleName": "rds-desired-instance-type",
		"RiskLevel": 1,
		"InputParameters": {
			"instanceTypes": "rds.mysql.s2.large"
		}
	}
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|ConfigRuleNotExists|The ConfigRule does not exist.|此规则不存在。|
|503|ServiceUnavailable|The request has failed due to a temporary failure of the server.|服务不可用。|
|404|AccountNotExisted|Your account does not exist.|您的账号不存在。|
|400|NoPermission|You are not authorized to perform this operation.|您无权执行此操作。|

访问[错误中心](https://error-center.aliyun.com/status/product/Config)查看更多错误码。

