(1)請說明 Fixnum (整數) 和 Float (浮點數) 之間的差異

儲存於31位元空間內的整數都是Fixnum
有小數點的都是Float浮點數


(2)今天有兩個字串：

str1 = "Hallo Welt!" 
str2 = " NTU Rails 261!"
請說明以下兩個印出字串的方式的不同處：

puts str1 + str2
Hallo Welt!NTU Rails 261!

puts "#{str1}#{str2}"
Hallo Welt!NTU Rails 261!

以上兩者都是印出相同的字串，但是puts str1 + str2 用加號連接的字串會耗盡許多記憶體 ，而可以用字串內差puts "#{str1}#{str2}"比較有效率


(3)請解釋 array 和 hash 的不同處?

array只會有正數，且索引值從零開始
Ruby on Rails 的效率Hush功能比array好，可以呈現任何純量


(4)請寫一段 code 從 [1, "a string", 3.14, [1,2,3,4]] 這個陣列找出所有非字串的值

Arr.reject{|x| x.class == String}

(5)請列出兩種產出亂數的方法?

rand(1..9) 
(1..9).to_a.shuffle.last

(6)
以下這段程式碼：
((1 > 3)&&(true == true))||(!!!false)
會執行出什麼結果？ 請試試不用 irb 算出結果

Ture


(7)請把 lesson1 程式碼裡的 calculator.rb 裡面的使用者輸入兩個數字的方式改寫成 method，並要有防止使用者亂輸入值的功能
(這題我不會寫啊～～～～～參考同學的～～)

先從String增加一個方法，使Ruby可以判斷string是否為float:

class String
    def is_number?
      true if Float(self).rescue false
    end
end

然後再加入

def user_input
  begin
    puts "please enter the first number:"
    num1 = gets.chomp
  end until num1.is_number? == true
  Float(num1)
end



(8)請問 binding.pry 是什麼？ 要如何使用它？

pry 會自動攔下 request，跳出 console 供開發者 debug
在程式碼裡面插入 binding.pry
console裡直接加pry然後加上所要執行的程式，即可debug


(9)下面的一段程式碼，請嘗試用其他方法把 if...else...end 簡化成一行

var = 5

if var >= 5
  return "var is greater than or equal to 5"
else
  return "var is less than 5"
end


return var>=5 ?  “var is greater than or equal to 5” : ” var is less than 5”

