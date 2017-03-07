# checkio

## Non-unique Elements

```python
def checkio(x_list=[]):
    x_tuple = tuple(x_list)
    for i in x_tuple:
        if x_list.count(i) == 1:
            x_list.remove(i)
    print x_list
```

## roman-numerals 

����������Դ�ڹ��������ϵͳ�������ǻ�����ĸ����ض���ĸ����ϣ�����ʾ����������Щ������ӣ�������������õ�������ǰʮλ�����������ǣ�

I��II��III��IV��V��VI��VII��VIII��IX��X��

�������ϵͳ����ֱ�ӵ�ʮ����Ϊ��������û���㡣���������Ǹ������߸����ŵ���ϣ�

����ֵ

```shell
I 1 (unus)
V 5 (quinque)
X 10 (decem)
L 50 (quinquaginta)
C 100 (centum)
D 500 (quingenti)
M 1,000 (mille)
```

�������Ĺ����������ֵ���Ϣ���Բο� ά���ٿƵ�����.

������������Ӧ�÷��ظ���ָ��������ֵ�ķ�Χ��1��3999���������֡�

����: һ������ (int).

���: һ���ַ�����ʽ���������� (str).

����:

```shell
checkio(6) == 'VI'
checkio(76) == 'LXXVI'
checkio(13) == 'XIII'
```

���ʹ�ã� ����һ���н������������������ȥ̽����ͬ�ļ���ϵͳ�����������������徭��ʹ�ã���Ҳ���Ա������ı����ɡ�����������źͻ�ʯ��д���������֡���Щ�������ִ������������������;������� ���� �˽���......���ߣ�Ҳ�����������һ�����ԹŴ�����Ŀͻ�;-)

ǰ��: 0 < number < 4000

import sys

def checkio(a_num):
    num_dir = {1:'I',2:'II',3: 'III',4: 'IV',5: 'V',6 :'VI',7: 'VII',8 :'VIII',9: 'IX',10: 'X',20:'XX',30:'XXX',40:'XL',50: 'L',60:'LX',70:'LXX',80:'LXXX',90:'XC',100: 'C',200:'CC',300:'CCC',400:'CD',500: 'D',600:'DC',700:'DCC',800:'DCCC',900:'CM',1000: 'M',2000:'MM',3000:'MMM'}

    a_str = str(a_num)
    len_num = len(a_str)
    roman_list = []
    for i in range(0,len_num):
        xx_num = len_num-i-1
        ww = int(a_str[i])*10**xx_num
        if ww == 0:
                continue
        else:
            roman_list.append(num_dir[ww])

    print ''.join(roman_list)

checkio(3999)

# ����ѡ���⿼�Գɼ����ű�

1. ѧ���Ĵ��ⶼ�Ǳ������ı��ĵ��У���ѧ��������һ��ռһ�У����ִ�Сд��
2. �𰸱���Ϊ00�ļ�

```shell
[root@mastera stutest]# ls
00  10  11  13  16  17  18  19  2  20  24  25  26  27  28  3  31  35  4  43  45  46  5  55  56  58  6  7  9  ule_check.py
```

���ű�����
```python
#!/usr/lib/python
# -*- coding: utf-8 -*-


names=locals()
		 
a_list=[]
with open('00','r') as f:
	for i in f.readlines()[:50]:
		a_list.append(i.strip())

file_list=[2,3,4,5,6,7,9,10,11,13,16,17,18,19,20,24,25,26,27,28,31,35,43,45,46,55,56,58]

for f_num in file_list:
	f_str='%d'%f_num
	names['b_list%s' % f_num]=[]
	with open(f_str,'r') as f:
        	for i in f.readlines()[:50]:
                	names['b_list%s' % f_num].append(i.strip())
	num = 50

	if len(names['b_list%s' % f_num]) != 50:
		print('{}û�гɼ�'.format(f_num))	
		continue
	for i in range(0,50):
		if names['b_list%s' % f_num][i]!=a_list[i]:
			num = num - 1
	print('{}�ĳɼ�Ϊ��{}'.format(f_str,num*2))
```

���������:

```shell
[root@mastera stutest]# python ule_check.py 
2�ĳɼ�Ϊ��36
3û�гɼ�
4û�гɼ�
5�ĳɼ�Ϊ��74
6�ĳɼ�Ϊ��50
7�ĳɼ�Ϊ��74
9�ĳɼ�Ϊ��68
10�ĳɼ�Ϊ��68
11�ĳɼ�Ϊ��64
13�ĳɼ�Ϊ��82
16�ĳɼ�Ϊ��56
17�ĳɼ�Ϊ��66
18�ĳɼ�Ϊ��68
19�ĳɼ�Ϊ��66
20�ĳɼ�Ϊ��64
24�ĳɼ�Ϊ��60
25�ĳɼ�Ϊ��72
26�ĳɼ�Ϊ��58
27�ĳɼ�Ϊ��46
28�ĳɼ�Ϊ��44
31�ĳɼ�Ϊ��70
35�ĳɼ�Ϊ��52
43�ĳɼ�Ϊ��76
45�ĳɼ�Ϊ��0
46�ĳɼ�Ϊ��10
55�ĳɼ�Ϊ��64
56�ĳɼ�Ϊ��60
58�ĳɼ�Ϊ��70

```