# Structure
是一个[[marker interface]]。要让一个对象进行克隆，其实就是两个步骤 1. 让该类实现java.lang.Cloneable接口 2. 重写（override）Object类的clone()方法。如果没有implements Cloneable的类调用Object.clone()方法就会抛出CloneNotSupportedException。