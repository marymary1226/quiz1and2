#（1)請用簡單的方式敘述以下每一行程式碼:

a = 1 將變數a宣告為2
@a = 2 將instance value 設定為2
@@a = 5 class variable 設為5
user = User.new  新建立一個user 的物件
user.name  user物件中name欄位的sretting method 
user.name = "Joe" user 物件中name欄位的setting method



(2)什麼是 module? 請寫一段程式碼說明一個class要如何使用一個 module 裡面的 method?

module它跟Class類別非常相似，可以在裡面定義方法。只是不能用new來建立它。

module Knowledge
  def math
      puts 'I know chinese'
  end
end

class Teachter
  include Knowledge
end


bob = Teacher.new
bob.chinese


(3)請說明 class 和 instance variable 之間的差別

*instance variable (實例變數)是把資料綁定在object上的方法，只要被創出來的object還在，instance variable紀錄的資料也會存在
*class valuable 是綁定class本身的資料

（4）如果今天我為一個叫 User 的 class 產生一個新物件的方式是:

User.new("Bob", "male", "Engineer") 請寫出 User class 的 initialize method


class User
    attr_accessor :name, :gender, :job
    def initialize(name, gender, job)
        @name = name
        @gender = gender
        @job = job
    end
end


(5)self 在(a) class 裡，method 外面 (b) class 裡，instance method 裡 分別是指向什麼?
(a) class 裡，method 外面 :self 是指class自己
(b) class 裡，instance method 裡：self是指被創出的某object.


(6)attr_accessor 的功能是什麼

自動地將getter and setter method 寫好

(7)請說明 public 和 private method 之間的不同

public method :大家都可以直接存取，大家都可以看到
private method:只在內部才能存取，希望method 不會被其他程式使用到

(8)Ruby 是如何確保一個 module 的 method 會被 include 它的 class 使用到？ (提示：method lookup)

Include的祖先module會先被找到，因為使用.ancestors會發現它夾在sub class與parent class之間


