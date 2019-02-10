# Factory-Patterm
工厂方法模式代码例子

设计模式-工厂方法模式（Fatory Patterm）
1、是什么是工厂模式?

2、什么时候使用工厂模式?

　　主要用于生成产品族

3、工厂模式使用的好处?

　　好处：类变少了，代码得到统一了

　　缺点: 1、代码量容易泛滥

　　　　 2、不能描述产品与产品之间的关系

　　　

4、实例：
    
    
            /*定义一个人的接口*/
      public interface Person  {
          /*名字*/
          String getName();
      }

      public class CityPerson implements Person {
          @Override
          public String getName() {
              return  "city person";
          }
      }

      //村民
      public class Villager implements Person {
          @Override
          public String getName() {
              return "you are a villager";
          }
      }


      /*定义工厂方法模式*/
      public interface PersonsFactory {
          //定义一个创建人的接口
          Person createPerson();
      }

      /*实现这个接口*/
      public class CityPersonFactory implements PersonsFactory {
          @Override
          public Person createPerson() {
              return new CityPerson();
          }
      }


      public class VillagerFactory implements PersonsFactory {
          @Override
          public Person createPerson() {
              return new Villager();
          }
      }

      public class Test {

      public static void main(String[] args) {
          PersonsFactory p = null;
          p = new CityPersonFactory();
          System.out.println(p.createPerson().getName());
          p = new VillagerFactory();
          System.out.println(p.createPerson().getName());
      }

    }
  
