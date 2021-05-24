# 说明
jdk5引入，可以说是[[marker interface]] 功能的拓展，需要指定[[Retention]]和[[Target]]（这2个也是注解）。比如
``
@Retention(RetentionPolicy.RUNTIME) @Target(ElementType.ANNOTATION\_TYPE)
public @interface Target
``

使用@interface自定义注解时，自动继承了java.lang.annotation.Annotation接口，其中的每一个方法实际上是声明了一个配置参数。方法的名称就是参数的名称，返回值类型就是参数的类型（返回值类型只能是基本类型、Class、String、enum）。可以通过default来声明参数的默认值。

也可以自定义参数，参数类型限制为int，long，double，String，Class，枚举，其他注解类型，上面类型的数组。例如定义为`int value();String name();String[] addresses();` 使用 
``
@CustUserAnnotation(value = 100, name="jack ma",addresses = {"人民路","江西路"}) 
public class CustUser { }
``
也可以使用default提供默认值` public String tableName() default "className";`运行时获取`Annotation[] annotations= custUser.getClass().getAnnotations();` 编译时获取比如自定义processors需要实现javax.annotation.processing.Processor接口（maven编译） 