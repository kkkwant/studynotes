## PSR-1规范

> psr-1 制定了代码的基本规范 包括类、文件等

- php代码`必须`使用<?php ?> 长标签或者 <?=?>短标签，不能使用自己的自定义标签
- php代码`必须`只能使用不包含bom的utf8文件编码
- 从属效应（副效果）
- 命名空间以及类的命名必须遵循psr-4的规范

	1. 每个类独立成一个文件，且命名空间至少要有一个层次。
	2. 类的命令必须遵循大写字母开头的驼峰命名规范
- 类的常量中所有字母必须大写，词语之间以下划线分割 如 MY_NAME PHP_VERSION
- 类的属性必须遵循小写字母开头的驼峰写法 如 firstName
- 类的方法必须符合小写字母开头的驼峰的写法 如 function getName()


## PSR-2 

> PSR-2规范规定了php代码规范的规则。是psr-1的延伸和拓展

- php文件规范

	1. 文件必须使用Unix LF作为行的结束符
	2. php文件必须以一个空白行作为结束
	2. 所有的php文件必须以省略掉文件末尾的 ?>
- php 行 规范
   
	1. 一行代码的长度不能有硬性的约束，但是一定要下限制在120行个字符以内。超过此字符，带有代码检查代码规范的编辑器要发出警告
	2. 每行代码不应该多余80个字符，多余80个字符应折成多行
	3. 非空行后一定不能有多余的空格符
	4. 空行可以使代码阅读更加方便以及有利于代码的分块
	5. 每行一定不能存在多条语句 比如 echo '1';echo '2';
	
- php 代码缩进

	1. 代码必须使用空格符作为缩进，一定不能用tab键
	

- php 关键字规范

	1. php中所有的关键字应该必须为全部小写。 常量true false null 也必须为小写 

- php 命名空间以及use 声明

	1. 所有use 必须在namespace后声明 
	2. 每条use声明语句必须只有一个use关键字
	3. use语句必须使用一个空白行
	4. 
			<?php 
			
				namespace A;
				
				use A\C;
				
				class B{}

- php 类 属性、方法

	1. 关键字extends 和implements 必须卸载类名字的后面的同一行
	2. 类的开始和结束的花括号必须独自占用一行
	3. 类的属性必须添加访问修饰符
	4. 一定不能再使用var声明一个属性
	5. 每行语句必须不可定义多个属性
	6. 不要使用下划线来作为前缀来区分属性是protected 还是private
	7. 类的所有的方法也必须添加访问修饰符 不能使用下划线区分proteted或者private
	8. 类的方法开始必须独占一行，参数左右括号之间不能有空格
	9. 类的方法的参数 逗号后面必须有一个空格，逗号前面一定不能有空格，有默认值的一定要放到末尾
	10. 类的方法的参数，可以分成多列，但是拆成多列的参数 每个参数必须单独成行
	11. 类的方法的开始括号要和方法在一行。
	12. abstract final 以及static 需要添加声明的时候，staic 必须写在其后面

			final public static function test()
	13. 方法以及函数调用 同8、9


- php 控制结构

	1. 控制结构关键词后面必须要有一个空格
	2. 左括号后不能有空格  后括号前不能有空格
	3. 右括号( 和开始花括号之间要有一个空格
	4. 结束的花括号一定在单独成行

			if ($condition) {
				
			}
	5. if 结构留意括号 空格 else 要和前面的花括号在一行

			if ($condition) {
				# code...
			} else {
				# code...
			}
	6. 标准的for 和foreach try catch 注意其括号和空格以及你花括号的位置

			foreach($arr as $key=> $v){
			}
			
			for($i=0; $i<10; $i++) {
			}

## PSR-3 日志接口规范

> 日志接口规范是为了让日志类库更简单，

1. 日志接口对外定义8个方法。分别记录八个等级的错误。 debug 、info、notice、warning、error、critical、alert 以及emergency

## PSR-4

> 一个完整的类具有以下结构

		\命名空间\子命名空间\类名

- 完整的类名必须有一个或多个子命名空间
- 完整的类名必须有一个顶级的命名空间
- 完整的类名必须必须有一个最终的类名
- 完整的类名中含有下划线是没有任何意义的
- 完整的类名可以由任意的大小写字母组成
- 完整的类名必须是大小写敏感的

- 完整的类名中，去掉最前面的命名空间分隔符，前面连续的一个或者多个命名空间，作为命名空间前缀，其必须与至少一个文件基目录相对应
- 紧接命名空间的前缀子命名空间，必须与相对应的文件基目录向匹配。其中的命名空间分隔符作为目录的分隔符。
- 末尾的类名必须以.php为后缀的文件同名
- 自动加载器的实现，一定不能抛出异常，一定不能触发任一级别的错误。

 