# iOS-知识点总结
1、风格纠错题

2、优化部分

3、硬伤部分

4、什么情况使用 weak 关键字，相比 assign 有什么不同？

5、怎么用 copy 关键字？

6、这个写法会出什么问题： @property (copy) NSMutableArray *array;

7、如何让自己的类用 copy 修饰符？如何重写带 copy 关键字的 setter？

8、@property 的本质是什么？ivar、getter、setter 是如何生成并添加到这个类中的

9、@protocol 和 category 中如何使用 @property

10、runtime 如何实现 weak 属性

11、@property中有哪些属性关键字？/ @property 后面可以有哪些修饰符？

12、weak属性需要在dealloc中置nil么？

13、@synthesize和@dynamic分别有什么作用？

14、ARC下，不显式指定任何属性关键字时，默认的关键字都有哪些？

15、用@property声明的NSString（或NSArray，NSDictionary）经常使用copy关键字，为什么？如果改用strong关键字，可能造成什么问题？

16、对非集合类对象的copy操作

17、集合类对象的copy与mutableCopy

18、@synthesize合成实例变量的规则是什么？假如property名为foo，存在一个名为_foo的实例变量，那么还会自动合成新变量么？

19、在有了自动合成属性实例变量之后，@synthesize还有哪些使用场景？

20、objc中向一个nil对象发送消息将会发生什么？

21、objc中向一个对象发送消息[obj foo]和objc_msgSend()函数之间有什么关系？

22、什么时候会报unrecognized selector的异常？

23、一个objc对象如何进行内存布局？（考虑有父类的情况）

24、一个objc对象的isa的指针指向什么？有什么作用？

25、下面的代码输出什么？

   @implementation Son : Father
   - (id)init
   {
       self = [super init];
       if (self) {
           NSLog(@"%@", NSStringFromClass([self class]));
           NSLog(@"%@", NSStringFromClass([super class]));
       }
       return self;
   }
   @end
   25. _objc_msgForward 函数是做什么的，直接调用它将会发生什么？
26. runtime如何实现weak变量的自动置nil？
27. 能否向编译后得到的类中增加实例变量？能否向运行时创建的类中添加实例变量？为什么？
28. runloop和线程有什么关系？
29. runloop的mode作用是什么？
30. 以+ scheduledTimerWithTimeInterval...的方式触发的timer，在滑动页面上的列表时，timer会暂定回调，为什么？如何解决？
31. 猜想runloop内部是如何实现的？
32. objc使用什么机制管理对象内存？
33. ARC通过什么方式帮助开发者管理内存？
34. 不手动指定autoreleasepool的前提下，一个autorealese对象在什么时刻释放？（比如在一个vc的viewDidLoad中创建）
35. BAD_ACCESS在什么情况下出现？
36. 苹果是如何实现autoreleasepool的？
37. 使用block时什么情况会发生引用循环，如何解决？
38. 在block内如何修改block外部变量？
39. 使用系统的某些block api（如UIView的block版本写动画时），是否也考虑引用循环问题？
40. GCD的队列（dispatch_queue_t）分哪两种类型？
41. 如何用GCD同步若干个异步调用？（如根据若干个url异步加载多张图片，然后在都下载完成后合成一张整图）
42. dispatch_barrier_async的作用是什么？
43. 苹果为什么要废弃dispatch_get_current_queue？
44. 以下代码运行结果如何？
- (void)viewDidLoad
{
   [super viewDidLoad];
   NSLog(@"1");
   dispatch_sync(dispatch_get_main_queue(), ^{
       NSLog(@"2");
   });
   NSLog(@"3");
}
45. addObserver:forKeyPath:options:context:各个参数的作用分别是什么，observer中需要实现哪个方法才能获得KVO回调？
46. 如何手动触发一个value的KVO
47. 若一个类有实例变量 NSString *_foo ，调用setValue:forKey:时，可以以foo还是 _foo 作为key？
48. KVC的keyPath中的集合运算符如何使用？
49. KVC和KVO的keyPath一定是属性么？
50. 如何关闭默认的KVO的默认实现，并进入自定义的KVO实现？
51. apple用什么方式实现对一个对象的KVO？
52. IBOutlet连出来的视图属性为什么可以被设置成weak?
53. IB中User Defined Runtime Attributes如何使用？
54. 如何调试BAD_ACCESS错误
55. lldb（gdb）常用的调试命令？
