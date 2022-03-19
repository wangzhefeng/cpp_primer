
C++ 编译
================

1.操作系统与编译器
---------------------------

   - 编译器


2.编译
---------------------------





2.1 程序源文件命名约定
~~~~~~~~~~~~~~~~~~~~~~~~~~~

   - ``.cc``
   - ``.cxx``
   - ``.cpp``
   - ``.cp``
   - ``.C``

2.1 从命令行运行编译器
~~~~~~~~~~~~~~~~~~~~~~~~~~~

- 在不同操作系统和编译器系统中, 运行 C++ 编译器的命令也各不相同, 最常用的编译器是 GUN 编译器和微软的 Visual Studio 编译器

   - 默认情况下, 运行 GNU 编译器的命令是 ``g++``

      .. code-block:: shell

         $ g++ -o prog prog.cc

   .. note:: 

      - ``-o prog`` 是编译器参数, 指定了可执行文件的文件名. 
        如果不省略该参数, 在 Windows 中生成 ``prog.exe`` 文件; 在 UNIX 系统中生成 ``prog`` 文件;
        如果省略该参数, 在 Windows 中生成 ``prog.exe`` 文件; 在 UNIX 系统中生成 ``prog.out`` 文件
      - 根据使用的 GNU 编译器的版本, 可能需要指定 ``-std=c++0x`` 参数来打开对 C++11 的支持
   

- Windows

   .. code-block:: shell

      $ CC prog.cc

   - ``CC`` 是编译器程序的名字, 编译器生成一个可执行文件, Windows 系统会将这个可执行文件命名为 ``prog.ext``
   - Windows 系统中运行一个可执行文件需要提供可执行文件的文件名, 可以省略其扩展名

      .. code-block:: shell
      
         $ prog
         $ .\prog
   
   - Windows 系统中访问 main 返回值, 执行完一个程序后, 可以通过 ``echo`` 命令获得其返回值

      .. code-block:: shell

         $ echo %ERRORLEVEL%

- UNIX

   .. code-block:: shell

      $ CC prog.cc
      $ g++ -o compiled_file compile_file.cc

   - ``CC`` 是编译器程序的名字, 编译器生成一个可执行文件, UNIX 系统会将这个可执行文件命名为 ``prog.out``
   - UNIX 系统中运行一个可执行文件需要使用全文件名, 包括文件扩展名

      .. code-block:: shell
      
         $ prog.out
         $ ./prog.out
   
   - UNIX 系统中访问 main 返回值, 执行完一个程序后, 可以通过 ``echo`` 命令获得其返回值

      .. code-block:: shell

         $ echo $?

.. note:: 

   - 从键盘输入文件结束符

     - Windows: ``Ctrl+z`` + ``Enter``
     - UNIX: ``Ctrl+d``

2.2 IDE 运行编译器
~~~~~~~~~~~~~~~~~~~~~~~~~~
      
   - 运行 Visual Studio 2010 编译器的命令是 ``cl``:

      .. code-block:: shell

         C:\Users\me\Programs> cl /EHsc prog.cc
   
      - ``cl`` 是编译器
      - ``/EHsc`` 是编译器选项, 用来打开标准异常处理

