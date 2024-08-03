# Полный стек вызовов недоступен

В зависимости от настроек Visual Studio, когда в Stride создается исключение, Visual Studio может отображать только стек вызовов из .DLL-файлов среды выполнения Stride или сборок .NET Framework, но не пользовательский код.

Чтобы прервать работу сразу после возникновения исключения, добавьте дополнительные условия в Visual Studio **Параметры исключений (Exception Settings)**.

1. На панели инструментов Visual Studio, в меню **Отладка (Debug)** , select **Окна > Параметры исключений (Windows > Exception Settings)**. 

    ![Exception settings](media/exception-settings.png)

2. Разверните **Common Language Runtime Exceptions** и выберите **All Common Language Runtime Exceptions not in this list**. Возможно, вам придется выбрать и другие условия.

    ![Все исключения среды CLR, не указанные в этом списке](media/all-common-language-runtime-exceptions.png)

>[!Подсказка]
>Чтобы восстановить список исключений по умолчанию, щелкните правой кнопкой мыши и выберите **Восстановить значения по умолчанию (Restore Defaults)**.

Дополнительную информацию об управлении исключениями в Visual Studio см.[Управление исключениями с помощью отладчика в Visual Studio](https://docs.microsoft.com/en-us/visualstudio/debugger/managing-exceptions-with-the-debugger) в документации Microsoft Visual Studio.