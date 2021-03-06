#				EditText

## 限制输入的小技巧

1. 						inputType
1. 						setFilters
1. 						TextWatcher 
1. 						digits
         * 							DigitsKeyListener
         * 							android:digits

## 焦点

 3. 					父布局设置两个属性失去焦点

```java
	Parent.setFocusable(true);
	Parent.setFocusableInTouchMode(true);
	android:focusable="true"
	android:focusableInTouchMode="true"
```

2. EditText自动获取焦点并弹出键盘

```java
EditText.setFocusable(true);  
EditText.setFocusableInTouchMode(true);
EditText.requestFocus();

```

## TextWatcher

* beforeTextChanged

    输入过程中执行该方法

* onTextChanged

     输入前确 认执行该方法

* afterTextChanged

     输入结束 执行该方法

## 光标/游标

1. 默认读取 colorAccent  

   如果全局统一修改的话可以修改 colorAccent  

2. 或者定义成style 

3. 自定义光标

```
 android:textCursorDrawable="@drawable/color_cursor"
```

​	定义文件color_curso

```
<?xml version="1.0" encoding="utf-8"?>
<shape xmlns:android="http://schemas.android.com/apk/res/android" android:shape="rectangle">
        <size android:width="1dp" />
        <solid android:color="@color/textbule"  />
</shape>
```



## 底部横线

移除横线

```
android：background=“@null”
```



## 输入类型 setInputType

1. 下面是几个简单的例子：

        /**
         * 第一个例子：对用户可见的密码字段
         */
        editText.setInputType(InputType.TYPE_CLASS_TEXT |
                InputType.TYPE_TEXT_VARIATION_VISIBLE_PASSWORD);
    
        /**
         * 第二个例子：具有自动大写的多行邮寄地址
         */
        editText.setInputType(InputType.TYPE_CLASS_TEXT |
                InputType.TYPE_TEXT_VARIATION_POSTAL_ADDRESS |
                InputType.TYPE_TEXT_FLAG_MULTI_LINE);
    
        /**
         * 第三个例子：一个时间字段
         */
        editText.setInputType(InputType.TYPE_CLASS_DATETIME |
                InputType.TYPE_DATETIME_VARIATION_TIME);
2. 使用EditText的setInputType()方法设置输入类型：

    EditText editText;
    
    //输入类型为没有指定明确的类型的特殊内容类型
    editText.setInputType(InputType.TYPE_NULL);
    
    //输入类型为普通文本
    editText.setInputType(InputType.TYPE_CLASS_TEXT);
    
    //输入类型为数字文本
    editText.setInputType(InputType.TYPE_CLASS_NUMBER);
    
    //输入类型为电话号码
    editText.setInputType(InputType.TYPE_CLASS_PHONE);
    
    //输入类型为日期和时间
    editText.setInputType(InputType.TYPE_CLASS_DATETIME);
    
    //输入类型为{@link#TYPE_CLASS_DATETIME}的缺省变化值，允许输入日期和时间。
    editText.setInputType(InputType.TYPE_DATETIME_VARIATION_NORMAL);
    
    //输入类型为{@link#TYPE_CLASS_DATETIME}的缺省变化值，只允许输入一个日期。
    editText.setInputType(InputType.TYPE_DATETIME_VARIATION_DATE);
    
    //输入类型为{@link#TYPE_CLASS_DATETIME}的缺省变化值，只允许输入一个时间。
    editText.setInputType(InputType.TYPE_DATETIME_VARIATION_TIME);
    
    //输入类型为决定所给文本整体类的位掩码
    editText.setInputType(InputType.TYPE_MASK_CLASS);
    
    //输入类型为提供附加标志位选项的位掩码
    editText.setInputType(InputType.TYPE_MASK_FLAGS);
    
    //输入类型为决定基类内容变化的位掩码
    editText.setInputType(InputType.TYPE_MASK_VARIATION);
    
    //输入类型为小数数字，允许十进制小数点提供分数值。
    editText.setInputType(InputType.TYPE_NUMBER_FLAG_DECIMAL);
    //输入类型为数字是带符号的，允许在开头带正号或者负号
    editText.setInputType(InputType.TYPE_NUMBER_FLAG_SIGNED);
    
    //输入类型为{@link#TYPE_CLASS_NUMBER}的缺省变化值：为纯普通数字文本
    editText.setInputType(InputType.TYPE_NUMBER_VARIATION_NORMAL);
    
    //输入类型为{@link#TYPE_CLASS_NUMBER}的缺省变化值：为数字密码
    editText.setInputType(InputType.TYPE_NUMBER_VARIATION_PASSWORD);
    
    //输入类型为自动完成文本类型
    editText.setInputType(InputType.TYPE_TEXT_FLAG_AUTO_COMPLETE);
    
    //输入类型为自动纠正文本类型
    editText.setInputType(InputType.TYPE_TEXT_FLAG_AUTO_CORRECT);
    
    //输入类型为所有字符大写
    editText.setInputType(InputType.TYPE_TEXT_FLAG_CAP_CHARACTERS);
    
    //输入类型为每句的第一个字符大写
    editText.setInputType(InputType.TYPE_TEXT_FLAG_CAP_SENTENCES);
    
    //输入类型为每个单词的第一个字母大写
    editText.setInputType(InputType.TYPE_TEXT_FLAG_CAP_WORDS);
    
    //输入多行文本
    editText.setInputType(InputType.TYPE_TEXT_FLAG_IME_MULTI_LINE);
    
    //进行输入时，输入法无提示
    editText.setInputType(InputType.TYPE_TEXT_FLAG_NO_SUGGESTIONS);
    
    //输入一个短的，可能是非正式的消息，如即时消息或短信。
    editText.setInputType(InputType.TYPE_TEXT_VARIATION_SHORT_MESSAGE);
    
    //输入长内容，可能是正式的消息内容，比如电子邮件的主体
    editText.setInputType(InputType.TYPE_TEXT_VARIATION_LONG_MESSAGE);
    
    //输入文本以过滤列表等内容
    editText.setInputType(InputType.TYPE_TEXT_VARIATION_FILTER);
    
    //输入一个电子邮件地址
    editText.setInputType(InputType.TYPE_TEXT_VARIATION_EMAIL_ADDRESS);
    
    //输入电子邮件主题行
    editText.setInputType(InputType.TYPE_TEXT_VARIATION_EMAIL_SUBJECT);
    
    //输入一个密码
    editText.setInputType(InputType.TYPE_TEXT_VARIATION_PASSWORD);
    
    //输入老式的普通文本
    editText.setInputType(InputType.TYPE_TEXT_VARIATION_NORMAL);
    
    //输入人名
    editText.setInputType(InputType.TYPE_TEXT_VARIATION_PERSON_NAME);
    
    //输入邮寄地址
    editText.setInputType(InputType.TYPE_TEXT_VARIATION_POSTAL_ADDRESS);
    
    //输入语音发音输入文本，如联系人拼音名称字段
    editText.setInputType(InputType.TYPE_TEXT_VARIATION_PHONETIC);
    
    //输入URI
    editText.setInputType(InputType.TYPE_TEXT_VARIATION_URI);
    
    //输入对用户可见的密码
    editText.setInputType(InputType.TYPE_TEXT_VARIATION_VISIBLE_PASSWORD);
    
    //输入网页表单中的文本
    editText.setInputType(InputType.TYPE_TEXT_VARIATION_WEB_EDIT_TEXT);
    
    //输入网页表单中的邮件地址
    editText.setInputType(InputType.TYPE_TEXT_VARIATION_WEB_EMAIL_ADDRESS);
    
    //输入网页表单中的密码
    editText.setInputType(InputType.TYPE_TEXT_VARIATION_WEB_PASSWORD);
3. 在布局文件中使用android:inputType属性来设置：

    //输入类型为没有指定明确的类型的特殊内容类型
    android:inputType="none"
    
    //输入类型为普通文本
    android:inputType="text"
    
     //输入类型为数字文本
     android:inputType="number"
    
    //输入类型为电话号码
     android:inputType=”phone”
    
    //输入类型为日期和时间
     android:inputType=”datetime”
    
     //输入类型为{@link#TYPE_CLASS_DATETIME}的缺省变化值，只允许输入一个日期。
     android:inputType=”date”
    
     //输入类型为{@link#TYPE_CLASS_DATETIME}的缺省变化值，只允许输入一个时间。
     android:inputType=”time”
    
    //输入类型为小数数字，允许十进制小数点提供分数值。
     android:inputType="numberDecimal"
    
    //输入类型为数字是带符号的，允许在开头带正号或者负号
     android:inputType="numberSigned"
    
    //输入类型为数字密码
     android:inputType="numberPassword"
    
    //输入类型为自动完成文本类型
     android:inputType="textAutoComplete"
    
    //输入类型为自动纠正文本类型
     android:inputType="textAutoCorrect"
    
    //输入类型为所有字符大写
     android:inputType="textCapCharacters"
    
    //输入类型为每句的第一个字符大写
     android:inputType="textCapSentences"
    
    //输入类型为每个单词的第一个字母大写
     android:inputType="textCapWords"
    
    //输入法多行文本
     android:inputType="textImeMultiLine"
    
    //进行输入时，输入法无提示
     android:inputType="textNoSuggestions"
    
     //输入一个短的，可能是非正式的消息，如即时消息或短信。
     android:inputType="textShortMessage"
    
    //输入长内容，可能是正式的消息内容，比如电子邮件的主体
     android:inputType="textLongMessage"
    
    //输入文本以过滤列表等内容
     android:inputType="textFilter"
    
    //输入一个电子邮件地址
     android:inputType="textEmailAddress"
    
    //输入电子邮件主题行
     android:inputType="textEmailSubject"
    
    //输入一个密码
     android:inputType="textPassword"
    
    //输入对用户可见的密码
     android:inputType="textVisiblePassword"
    
    //输入人的姓名
     android:inputType="textPersonName"
    
    //输入邮寄地址
     android:inputType="textPostalAddress"
    
    //输入语音发音输入文本，如联系人拼音名称字段
     android:inputType="textPhonetic"
    
    //输入URI
     android:inputType="textUri"
    
    //输入网页表单中的文本
     android:inputType="textWebEditText"
    
    //输入网页表单中的邮件地址
     android:inputType="textWebEmailAddress"
    
    //输入网页表单中的密码
     android:inputType="textWebPassword"