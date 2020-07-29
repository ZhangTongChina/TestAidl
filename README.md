# Aidl

## Aidl 修饰符
  in:表示数据只能有客户端传递到服务端，基本类型默认只支持in修饰符。
  
  out:表示参数数据只能由服务端传递到客户端。即服务端如果修改了参数对象的值，那么客户端的值也会变化，但服务端无法读取客户端对象的值。
  
  inout:表示参数数据能双向传值。
  
## 基本实现
  1.创建Aidl接口文件
  
  2.创建远程Sercive(实现Aidl文件中的接口)
  
  3.客户端链接Binder(服务端与客户端的Aidl包名路径要一致)
  
## Service回调Ancicity
  service增加两个接口用于注册和解注册:
  
   ```
   //注册回调
   void registerCallback(IOnNewBookArrivedListener  listener);
   ```

   ```
   //解注册回调
   void unregisterCallback(IOnNewBookArrivedListener  listener);
   ```
  
  为client端增加aidl文件，用于接收service端的回调
