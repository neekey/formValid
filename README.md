һ���򵥵ı���֤���
======================

���ڼ򵥵Ŀ��ǣ�û����Ӵ�����ʾ�������ṩ����֤�����Ϣ�����û��Զ���������Ĵ���

ʹ����class�������Ӧ�ؼ������ƶ���֤����ķ�ʽ

֧�ֶ��ع����Զ�����򣬲�����ʹ��������ʽ��ƥ�����

������KISSY 1.1.6
====

example
=======

<form id="formID">
	<input type="text" class="required max10" />
</from>


var form = KISSY.formValid( 'formID', function( result, elem, rule, msg){
	if( resule ){
	 	console.log( 'field: ' + elem.name + 'pass rule: ' + rule );
	}
	else {
		console.log( 'field: ' + elem.name + 'failed! error info:' );
		console.log( msg );
	}
})

API
=======

formValid( id, cb, rule )

������캯��

  - id ��id
  - cb ÿ���ֶα���֤��Ļص�����
  - �Զ������

check()

���������

submit( ifCheck )

�ύ��

  - ifCheck true�������false�򲻼��ֱ���ύ��Ĭ��Ϊfalse

��������
=========

rule = {
	'ruleName': {
		test: function( elem ){
			/* do the check remenber to return true/false */
		},
		msg: 'error info'
	}
}

**��������֧��������ʽ��ע���ַ���ת��**

���磬��󳤶�  'max\\d+'