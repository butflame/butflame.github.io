---
layout: post
title:  "ruby代码风格指南 by airbnb"
category: tech
date: 2021-02-03 23:07:22 +0800
tags: ruby
---
如题

> 全文译自 [airbnb - ruby style guide](https://github.com/airbnb/ruby)

---

## 空格的使用

### 缩进
* <a name="default-indentation"></a>
缩进应为两个空格的`soft-tab`
<sup>[[link](#default-indentation)]</sup>

* <a name="indent-when-as-case"></a>
`when`和`case`应在同一层缩进
<sup>[[link](#indent-when-as-case)]</sup>

	```ruby
	case
	when song.name == 'Misty'
	  puts 'Not again!'
	when song.duration > 120
	  puts 'Too long!'
	when Time.now.hour > 21
	  puts "It's too late"
	else
	  song.play
	end

	kind = case year
	       when 1850..1889 then 'Blues'
	       when 1890..1909 then 'Ragtime'
	       when 1910..1929 then 'New Orleans Jazz'
	       when 1930..1939 then 'Swing'
	       when 1940..1950 then 'Bebop'
	       else 'Jazz'
	       end
	```

* <a name="align-function-params"></a>
函数的参数要么都在同一行，要么每个占一行
<sup>[[link](#align-function-params)]</sup>


	```ruby
	# bad
	def self.create_translation(phrase_id, phrase_key, target_locale,
	                            value, user_id, do_xss_check, allow_verification)
	  ...
	end

	# good
	def self.create_translation(phrase_id,
	                            phrase_key,
	                            target_locale,
	                            value,
	                            user_id,
	                            do_xss_check,
	                            allow_verification)
	  ...
	end

	# good
	def self.create_translation(
	  phrase_id,
	  phrase_key,
	  target_locale,
	  value,
	  user_id,
	  do_xss_check,
	  allow_verification
	)
	  ...
	end
	```

* <a name="indent-multi-line-bool"></a>
在多行的布尔表达式中，对后续的行进行缩进
<sup>[[link](#indent-multi-line-bool)]</sup>

	```ruby
	# bad
	def is_eligible?(user)
	  Trebuchet.current.launch?(ProgramEligibilityHelper::PROGRAM_TREBUCHET_FLAG) &&
	  is_in_program?(user) &&
	  program_not_expired
	end

	# good
	def is_eligible?(user)
	  Trebuchet.current.launch?(ProgramEligibilityHelper::PROGRAM_TREBUCHET_FLAG) &&
	    is_in_program?(user) &&
	    program_not_expired
	end
	```

---

### 行内
* <a name="trailing-whitespace"></a>
永远不要在行尾留下空格
<sup>[[link](#trailing-whitespace)]</sup>


* <a name="space-before-comments"></a>
在同一行内写注释时，在代码和注释中间插入一个空格
<sup>[[link](#space-before-comments)]</sup>
	```ruby
	# bad
	result = func(a, b)# we might want to change b to c

	# good
	result = func(a, b) # we might want to change b to c
	```

* <a name="spaces-operators"></a>
在操作符附近加上空格，如逗号、冒号、分号之后，`{`前后 以及`}`之前
<sup>[[link](#spaces-operators)]</sup>
	```ruby
	sum = 1 + 2
	a, b = 1, 2
	1 > 2 ? true : false; puts 'Hi'
	[1, 2, 3].each { |e| puts e }
	```

* <a name="no-space-before-commas"></a>
永远不要在逗号之前加空格
<sup>[[link](#no-space-before-commas)]</sup>
	```ruby
	result = func(a, b)
	```



* <a name="spaces-block-params"></a>
不要在`block parameter pipes`中加空格，
只在同个`block`的多个参数中间加空格，
并在`block parameter pipes`外侧加空格
<sup>[[link](#spaces-block-params)]</sup>
	```ruby
	# bad
	{}.each { | x,  y |puts x }

	# good
	{}.each { |x, y| puts x }
	```

* <a name="no-space-after-!"></a>
不要在`!`和其参数之间加空格
<sup>[[link](#no-space-after-!)]</sup>
	```ruby
	!something
	```

* <a name="no-spaces-braces"></a>
在`(`, `[`之后 或 `]`, `)`之前不要插入空格
<sup>[[link](#no-spaces-braces)]</sup>
    ```ruby
    some(arg).other
    [1, 2, 3].length
    ```


* <a name="no-spaces-string-interpolation"></a>
在字符串插值中不要使用空格
<sup>[[link](#no-spaces-string-interpolation)]</sup>

    ```ruby
    # bad
    var = "This #{ foobar } is interpolated."

    # good
    var = "This #{foobar} is interpolated."
    ```


* <a name="no-spaces-range-literals"></a>
在进行范围迭代时不要使用空格
<sup>[[link](#no-spaces-range-literals)]</sup>

    ```ruby
    # bad
    (0 ... coll).each do |item|

    # good
    (0...coll).each do |item|
    ```

### 换行
* <a name="multiline-if-newline"></a>
在出现多行`if`条件时，在条件之后插入一个空行，以区分条件和后面的代码块
<sup>[[link](#multiline-if-newline)]</sup>

    ```ruby
    if @reservation_alteration.checkin == @reservation.start_date &&
       @reservation_alteration.checkout == (@reservation.start_date + @reservation.nights)

      redirect_to_alteration @reservation_alteration
    end
    ```


* <a name="newline-after-conditional"></a>
在条件判断、代码块、`case`声明之后插入空行
<sup>[[link](#newline-after-conditional)]</sup>

    ```ruby
    if robot.is_awesome?
      send_robot_present
    end

    robot.add_trait(:human_like_intelligence)
    ```

* <a name="newline-different-indent"></a>
在不同缩进级别的代码之间不要插入空行(例如`class` 或 `module`的首行和代码块之间)
<sup>[[link](#newline-different-indent)]</sup>

    ```ruby
    # bad
    class Foo

      def bar
        # body omitted
      end

    end

    # good
    class Foo
      def bar
        # body omitted
      end
    end
    ```

* <a name="newline-between-methods"></a>
在函数之间插入恰好一个空行
<sup>[[link](#newline-between-methods)]</sup>

    ```ruby
    def a
    end

    def b
    end
    ```

* <a name="method-def-empty-lines"></a>
将函数划分为更符合逻辑的段落时，用一个空行来分隔代码
<sup>[[link](#method-def-empty-lines)]</sup>

    ```ruby
    def transformorize_car
      car = manufacture(options)
      t = transformer(robot, disguise)

      car.after_market_mod!
      t.transform(car)
      car.assign_cool_name!

      fleet.add(car)
      car
    end
    ```

* <a name="trailing-newline"></a>
每个文件末尾都应以恰好一个空行结束
<sup>[[link](#trailing-newline)]</sup>

## 行的长度
* 将每行代码控制在目视范围内，不应超过100个字符，除非你有无法抗拒的理由<sup>[[link](#line-length)]</sup>

## Commenting

> Though a pain to write, comments are absolutely vital to keeping our code
> readable. The following rules describe what you should comment and where. But
> remember: while comments are very important, the best code is
> self-documenting. Giving sensible names to types and variables is much better
> than using obscure names that you must then explain through comments.

> When writing your comments, write for your audience: the next contributor who
> will need to understand your code. Be generous — the next one may be you!

——[Google C++ Style Guide][google-c++]




[airbnb-javascript]: https://github.com/airbnb/javascript
[rubocop-guide]: https://github.com/rubocop-hq/ruby-style-guide
[github-ruby]: https://github.com/styleguide/ruby
[google-c++]: https://google.github.io/styleguide/cppguide.html
[google-c++-comments]: https://google.github.io/styleguide/cppguide.html#Comments
[google-python-comments]: https://google.github.io/styleguide/pyguide.html#Comments
[ruby-naming-bang]: http://dablog.rubypal.com/2007/8/15/bang-methods-or-danger-will-rubyist
[ruby-freeze]: https://blog.honeybadger.io/when-to-use-freeze-and-frozen-in-ruby/
[avoid-else-return-early]: http://blog.timoxley.com/post/47041269194/avoid-else-return-early


