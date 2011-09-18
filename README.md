#一个简单的表单验证组件

- 处于简单的考虑，没有添加错误提示，而是提供了验证结果信息，让用户自定义错误结果的处理
- 使用在class中添加相应关键字来制定验证规则的方式
- 支持多重规则，自定义规则，并可以使用正则表达式来匹配规则
- 依赖：KISSY 1.1.6

##example

    <form id="formID">
        <input type="text" class="required max10" />
    </from>
    <script>
    var form = KISSY.formValid( 'formID', function( result, elem, rule, msg){
        if( resule ){
            console.log( 'field: ' + elem.name + 'pass rule: ' + rule );
        }
        else {
            console.log( 'field: ' + elem.name + 'failed! error info:' );
            console.log( msg );
        }
    })
    </script>

##API

**formValid( id, cb, rule )** 组件构造函数

  - id 表单id
  - cb 每个字段被验证后的回调函数
  - 自定义规则

**check()** 检查整个表单

**submit( ifCheck )** 提交表单

  - ifCheck true则检查表单，false则不检查直接提交，默认为false

##规则设置

    rule = {
	'ruleName': {
		test: function( elem ){
			/* do the check remenber to return true/false */
		},
		msg: 'error info'
	}
    }

**规则名称支持正则形式，注意字符串转移**

比如，最大长度  'max\\d+'