Query EasyUI ���ü��ط�ʽ����

easyui��ʲô���Ͳ������ˣ��Ӵ���ǰ�˵ľ���û�ù����϶�ҲӦ����˵������Σ����Ĳ��ǽ������ṩ��calendar��tree����Щ�������ʹ�õģ���Щ�����Ͻ��ܶ�����ϸ�����ĵ�����Ҳ���١������Ǵ�easyui���ļ�Ŀ¼�ṹ����˵��̸һ��easyui���������ü��ط�ʽ��

 

���ü��ط�ʽ
easyui�ļ��ؿ��Է�Ϊ���ַ�ʽ����ʽһ������ʽ���أ�2������ʽ���ء��ھ������������ּ��ط�ʽ֮ǰ�������ȿ���easyuiĿ¼�ṹ��

 

Ŀ¼�ṹ
demo�ļ��У�һЩʾ��������ʽ��Ŀ��ɾ����

locale��һЩ��ͬ���Ե��ļ�����ʵ�Ƕ�easyui����չ����ֻ�뱣�������õ��������Ӧ���ļ���

plugins��easyui�ṩ�ĸ������ܵ��ļ�����ʹ�÷�ʽ�����ر��뱣������ʽһ���ؿ���ɾ����

src :���������Դ�ļ�������ȫ������ʵ��Щ���ܲ��ǿ�Դ�ģ�����ҵ��Ȩ�����û��Դ�ļ���������ɾ����

themes�����⣬����css�ļ���Ҫ�õ���ͼ���ļ�������ṩ5�ַ�񡣣�����ֻ����Ҫʹ�õķ�񣬲��Ҿ��嵽һ�������ַ�Ϊ�����֣�easyui.css����������css��easyui.css����������css�ĺϲ��������ڲ�ͬ�ļ��ط�ʽ��ֻ���õ�һ���֡���

easyloader.js�����ҳ�֮Ϊ�������ļ�����ʹ�÷�ʽһ����Ҳ���ᱻʹ�á�

jquery.easyui.min.js��easyui�����ļ�������plugins�������ļ��ϲ���Ľ������Щ����ʹ�÷�ʽһ���ر��뱣������ʽ�����ز���ʹ�õ�������ɾ�������ļ�����ɾ����û����ɣ��������������ң����Եġ�����

jquery.min.js��jquery�ļ���easyui�ǻ���jquery�ģ�����Ǳ���ġ�

 

��������һЩ��Ȩ�ļ��͸�����־֮��ģ��Ͳ�˵�ˡ�

 

�����������ص㣺jquery.easyui.min.js��plugins�������ļ��ϲ���Ľ�������嵽ĳ���������default������css��easyui.css�����µ���������css�ϲ�֮��Ľ����

�����͵����˲�ͬ�����ּ��ط�ʽ��

 

����ʽ����
<link rel="stylesheet" type="text/css" href="easyui/themes/default/easyui.css">
<link rel="stylesheet" type="text/css" href="easyui/themes/icon.css">
<script type="text/javascript" src="easyui/jquery.min.js"></script>
<script type="text/javascript" src="easyui/jquery.easyui.min.js"></script>
����Ҳ����õķ�ʽ�����ַ�ʽ�����easyui�ṩ�����й��ܣ�������ҳ���ϻ᲻���õĵ����򵥱�����

 

����ʽ����
<link rel="stylesheet" type="text/css" href="easyui/themes/icon.css">
<script type="text/javascript" src="easyui/jquery.min.js"></script>
<script type="text/javascript" src="easyui/jquery.easyloader.js"></script>
���ַ�ʽ����ԱȽ�����ֻ����ʹ���ض����ܵ�ʱ��Ż�������Ӧ��plugins�µ�js�ͷ����css�ļ�����������ʹ�õĹ��ܶ�Ӧ��js��css��Զ���ᱻ���ء���easyloader.js���Ǹ������ڼ��ظ�������ġ�

 

����
ͬ������������ʹ�÷�ʽ����������ֻ�������ڷ�ʽ2���ù��̡�

��ҳ���а����磺

<a href="#" class="easyui-linkbutton" onclick="load1()">Load Calendar</a>
html�����classָ��easyui-linkbutton֮��easyui�ض��ı��ʱ��easyui���⵽���Զ���ȥ�������Ӧ���ļ�����Ӧ����Ӧ����ʽ�͹��ܡ�����easyui-linkbutton��Ǿ���ȥ����themes/default/linkbutton.css��plugins/jquery.linkbutton.js�������ļ���Ȼ��ı�a����ʾ��ʽ��

 

��Ȼ���ǿ����ֶ�ͨ��jsȥ������ع��ܣ�

using('calendar', function(){
                $('#cc').calendar({
                    width:180,
                    height:180
                });
            });
�����ͻ�ȥ����calendar�Ծ͵�css��js�ļ�������idΪcc��div�ϴ���һ�������ؼ���

 

����
�ܿ죬���Ǿͻᷢ��һЩ���⡣

 

���
��ʽ1�ļ�������ͨ������ themes/default/easyui.css��ָ�������ò�ͬ����µ�easyui.css��ʹ�ò�ͬ�ķ�񣬵��Ƿ�ʽ2���ǲ�û��ָ��������ָ�����

��ָ��ʱ��Ĭ��������default����µ���ʽ���ͻ�ȥ���ظ÷���µ���ʽ�������ʹ�÷�ʽ2ʱ��û��ָ����񣬲�����default���ͻ�������⡣

��Ȼ���ǿ�����ҳ����غ�ͨ��

easyloader.theme = "gray";
��ָ�����

 

����
ͬ���Ķ��������ļ������ڷ�ʽ1���ǿ���ֱ����ҳ������jquery.easyui.min.js�ĺ������á�

<script type="text/javascript" src="easyui/locale/easyui-lang-zh_CN.js"></script>
��������ڷ�ʽ2�ļ��أ����ǲ������õġ�

��Щ�����ļ���ʵ�ǶԸ������Ĭ�����õ��޸ģ����������û�м���ʱ�������ļ��������޸ĵ�Ȼ�ǲ��������õġ�

������ǿ���ͨ������

easyloader.locale = "zh_CN";
��ָ��ʹ�ú������ԡ�