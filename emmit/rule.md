# HTML速写之Emmet语法规则

1. html初使结构

   ！=> tab 可快速生成html结构

2. id(#)，class(.)

   ```
   div#box1 => <div id="box1"></div>
   div.box1 => <div class="box1"></div>
   ```

3. 子结点（>）,兄弟结点（+），父级节点（^）

   + 子结点（>）

     ```
     div>ul>li>p =>
     <div>
          <ul>
               <li>
                    <p></p>
                </li>
           </ul>
     </div>
     ```

   + 兄弟结点（+）

     ```
     div+ul+p =>
     <div></div>
     <ul></ul>
     <p></p>
     ```

   + 父级节点（^）

     ```
     div>ul>li^div =>
     <div>
          <ul>
              <li></li>
          </ul>
          <div></div>
     </div>
     ```

4. 重复（*）

   ```
   div*5 =>
   <div></div>
   <div></div>
   <div></div>
   <div></div>
   <div></div>
   ```

5. 分组（（））

   ```
   div>(ul>li>p)+div>P
   <div>
        <ul>
            <li>
                 <p></p>
            </li>
        </ul>
        <div>
             <p></p>
        </div>
   </div>
   ```

6. 属性（[attr]）

   ```
   a[href=123 :span=23] =>
   <a href="123" :span="23"></a>
   ```
   
7. 编号（$）

   ```
   ul>li.test$*3 =>
   <ul>
       <li class="test1"></li>
       <li class="test2"></li>
       <li class="test3"></li>
   </ul>
   ```

   **注意**
   
   ```
   一个$代表1个数，两个$$代表01，三个$$$代表001
   如果想自定义从几开始递增的话就利用：$@+数字数字
   例如：ul>li.test$@33
   ```
   
   
   
8. 文本（{}）

   ```
   ul>li.test$*3{测试$} =>
   <ul>
       <li class="test1">测试1</li>
       <li class="test2">测试2</li>
       <li class="test3">测试3</li>
    </ul>
   ```

   



[参考](https://blog.csdn.net/qq_33744228/article/details/80910377)

