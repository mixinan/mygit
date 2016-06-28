#indexOf

>####查找特定字符或字符串在当前字符串中的起始位置，如果不存在则返回-1

例如：

	String s = “abcded”;
	int index = s.indexOf(‘d’);
	int index1 = s.indexOf(‘h’);

	作用：返回字符d在字符串s中第一次出现的位置，结果为3
	由于字符h在字符串s中不存在，则index1 的值是-1

也可以从特定位置以后查找对应的字符，例如：

	String s = “abcded”;
	int index = s.indexOf(‘d’,4);
	
	作用：从字符串s第4位开始，找第一个出现的字符d
	结果：index 的值是5



另外一个类似的方法是lastIndexOf 方法，作用是从字符串的末尾开始向前查找第一次出现的指定字符或字符串，例如：

	String s = “abcded”;
	int index = s. lastIndexOf(‘d’);

	结果：index 的值是 5

#charAt

>####按照索引值(下标，从0开始)，获得字符串中的指定字符

例如：

	String s = “abc”;
    char c = s.chatAt(1);

	变量c 的值：'b'

#length

>####返回字符串的长度

例如：
	
	String s = “abc”;
    String s1 = “Java语言”;
    int len = s.length();
    int len1 = s1.length();

	变量len 的值：3
	变量len1 的值：6

#startsWith

>####判断字符串是否以某个字符串开始，如果是，则返回true

例如：

	String s = “TestGame”;
    boolean b = s.startsWith(“Test”);

	变量b 的值: true

类似的方法是**endsWith**，作用是判断字符串是否以某个字符串**结尾**，如果是，则返回true

例如：

    String s = “student.doc”;
    boolean b = s.endsWith(“doc”);
	
	变量b 的值：true

#split

>####以特定的字符串作为间隔，拆分当前字符串的内容，获得一个字符串数组

例如：
         
	String s = “ab,12,df”;
    String s1[] = s.split(“,”);

	作用：以”,”作为间隔，拆分字符串s
	结果：{“ab”,”12”,”df”}




#substring  
>####截取字符串中的一部分


例如：
         
	 String s = “Test”;
     String s1 = s.substring(2);
	
	作用：取字符串s中索引值为2(包括)以后的所有字符
	变量s1 的值："st"

如果需要取字符串内部指定的一部分，则可以使用带2个参数的方法，例如：

	String s = “TestString”;
    String s1 = s.substring(2,5);
	
	作用：取字符串s中从索引值2(包括)开始，到索引值5(不包括)的部分
	结果："stS"

#compareTo

>####比较两个字符串的大小，比较的原理是依次比较每个字符的字符编码

首先比较第一个字符，如果第一个字符串的字符编码大于第二个的字符串的字符编码，则返回1，如果小于则返回-1，如果相等则比较后续的字符，如果完全相同则返回0。
                            
例如：

	String s = “abc”;
	String s1 = “abd”;
	int value = s.compareTo(s1);

	value的值是小于0的值，即-1

在String类中还存在一个类似的方法**compareToIgnoreCase**，这个方法是忽略字符的大小写进行比较，比较的规则和compareTo一样。例如：

                                     
	String s = “aBc”;
	String s1 = “ABC”;
	int value = s. compareToIgnoreCase (s1);
	
	value的值是 0，即两个字符串相等
                            
                   
#replace

>####替换字符串中所有指定的字符，生成一个新的字符串。原来的字符串不变

例如：
	
	String s = “abcat”;
    String s1 = s.replace(‘a’,’1’);

	作用：将字符串s中所有的字符“a”替换成字符“1”
	新字符串s1的值："1bc1t"
	字符串s的内容不发生改变

如果需要将字符串中某个指定的**字符串**替换为其它字符串，则可以使用replaceAll方法。例如：

     String s = “abatbac”;
     String s1 = s.replaceAll(“ba”,”12”);

	作用：将字符串s中所有的字符串”ab”替换为”12”
	生成新的字符串：”a12t12c”
	字符串s的内容不发生改变

如果**只需要替换第一个**出现的指定字符串时，可以使用replaceFirst方法，例如：
        
	String s = “abatbac”;
    String s1 = s. replaceFirst (“ba”,”12”);
	
	作用：只将字符串s中第一次出现的字符串”ab”替换为字符串”12”
	字符串s1的值：”a12tbac”
	字符串s的内容也不发生改变

                   
#equals

>####判断两个字符串对象的内容是否相同。如果相同，则返回true

例如：
         
	String s = “abc”;
    String s1 = new String(“abc”);
    boolean b = s.equals(s1);

使用“==”比较的是两个对象在内存中存储的地址是否一样。例如上面的代码中，如果判断：
         
	boolean b = (s == s1);
	
	结果为：false
	因为s对象对应的地址是"abc"的地址，而s1使用new关键字申请新的内存
	内存地址和s的"abc"的地址不一样，所以结果为false

在String类中存在一个类似的方法**equalsIgnoreCase**，作用是**忽略大小写**比较两个字符串的内容是否相同。例如：

    String s = “abc”;
    String s1 =”ABC”;
	boolean b = s.equalsIgnoreCase(s1);

	变量b 的值：true


#getBytes

>####将字符串转换为对应的byte数组，从而便于数据的存储和传输

例如：

	String s = “计算机”;
    byte[] b = s.getBytes();   //使用本机默认的字符串转换为byte数组
    byte[] b = s.getBytes(“gb2312”); //使用gb2312字符集转换为byte数组
    
	在实际转换时，一定要注意字符集的问题，否则中文在转换时将会出现问题。

#toCharArray

>####和getBytes方法类似，将字符串转换为对应的char数组

例如：

	String s = “abc”;
    char[] c = s.toCharArray();

	字符数组c的值为：{'a', 'b', 'c'}
                   

#toLowerCase
>####将字符串中所有大写字符都转换为小写

例如：

	String s = “AbC123”;
	String s1 = s.toLowerCase();

	s1 的结果："abc123"
	字符串s 的值不变

类似的方法是**toUpperCase**，作用是将字符串中的小写字符转为大写。例如：

	String s = “AbC123”;
	String s1 = s.toUpperCase();

	结果为："ABC123"
	而字符串s 的值不变

#trim

>####去掉字符串开始和结尾的所有空格(不去掉中间的空格)


例如：

	String s = “   abc abc 123 “;
	String s1 = s.trim();

	值为："abc abc 123"