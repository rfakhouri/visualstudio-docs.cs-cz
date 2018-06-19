---
title: Ladění pomocí ladicího programu JIT | Microsoft Docs
ms.custom: ''
ms.date: 07/06/17
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- debugging [Visual Studio], Just-In-Time
- Just-In-Time debugging
ms.assetid: ee4d79a5-a1d2-4418-a93f-dd57a53e1836
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4f01dddf18e93c657d2c69e30a9b4698f4dda796
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
ms.locfileid: "34268136"
---
# <a name="debug-using-the-just-in-time-debugger-in-visual-studio"></a>Ladění pomocí ladicího programu JIT v sadě Visual Studio
Ladění za běhu spustí Visual Studio automaticky při výjimku nebo havárie v aplikaci, která běží mimo aplikaci Visual Studio. To umožňuje aplikaci otestovat, pokud neběží v sadě Visual Studio a zahájit ladění pomocí sady Visual Studio, když dojde k potížím.

Ladění za běhu funguje aplikací klasické pracovní plochy Windows. Pro univerzální aplikace pro Windows nefunguje a pro spravovaný kód, který je hostován v nativní aplikaci, například Vizualizérech nefunguje.

> [!TIP] 
> Pokud chcete vědět, jak reagovat na těsně v čase ladicího programu dialogové okno, najdete v části [v tomto tématu](../debugger/just-in-time-debugging-in-visual-studio.md).

##  <a name="BKMK_Enabling"></a> Povolit nebo zakázat pouze za běhu ladění  
Můžete povolit nebo zakázat pouze za běhu ladění ze sady Visual Studio **nástroje > Možnosti** dialogové okno.
  
#### <a name="to-enable-or-disable-just-in-time-debugging"></a>Chcete-li povolit nebo zakázat pouze za běhu ladění  
  
1.  Otevřete Visual Studio s oprávněními správce (klikněte pravým tlačítkem a zvolte **spustit jako správce**).

    Povolení nebo zakázání těsně za běhu, ladění, nastaví klíč registru a oprávnění správce, může být nutné změnit klíči.
    
2. Na **nástroje** nabídky, klikněte na tlačítko **možnosti**.
  
2.  V **možnosti** dialogové okno, rozbalte seznam **ladění** uzlu.  
  
3.  V **ladění** uzlu, vyberte **pouze za běhu**.

    ![Povolení nebo zakázání ladění JIT](../debugger/media/dbg-jit-enable-or-disable.png "povolení nebo zakázání ladění JIT") 
  
4.  V **ladění JIT povolit z těchto typů kódu** pole, zaškrtněte nebo zrušte typy relevantní program: **spravované**, **nativní**, nebo **skriptu**.    
  
5.  Click **OK**.  
  
Ladění za běhu může nadále povolené i v případě, že v počítači je již nainstalované sady Visual Studio. Když Visual Studio není nainstalována, nelze zakázat pouze za běhu ladění ze sady Visual Studio **možnosti** dialogové okno. V takovém případě můžete zakázat pouze za běhu ladění úpravou registru systému Windows.  
  
#### <a name="to-disable-just-in-time-debugging-by-editing-the-registry"></a>Chcete-li zakázat pouze za běhu ladění úpravou registru  
  
1.  Na **spustit** nabídky, Hledat a spustit `regedit.exe`  
  
2.  V **Editor registru** okno, vyhledejte a odstraňte následující položky registru:  
  
    -   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AeDebug\Debugger  
  
    -   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework\DbgManagedDebugger  

    ![Klíč registru JIT](../debugger/media/dbg-jit-registry.png "klíč registru JIT") 
  
3.  Pokud počítač používá 64bitový operační systém, odstraňte také následující položky registru:  
  
    -   HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows NT\CurrentVersion\AeDebug\Debugger  
  
    -   HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\. NETFramework\DbgManagedDebugger  
  
4.  Je třeba dbát na skrývá jiných klíčů registru.  
  
5.  Zavřít **Editor registru** okno.   
  
#### <a name="to-enable-just-in-time-debugging-of-a-windows-form"></a>Chcete-li povolit pouze za běhu ladění formuláře systému Windows  
  
1.  Ve výchozím nastavení mají formulářových aplikací Windows obslužnou rutinu výjimky nejvyšší úrovně, která umožňuje programu pokračovat ke spouštění, pokud lze obnovit. Například pokud aplikace Windows Forms neošetřenou výjimku, zobrazí se dialogové okno takto:  
  
     ![WindowsFormsUnhandledException](../debugger/media/windowsformsunhandledexception.png "WindowsFormsUnhandledException")  
  
     Chcete-li povolit pouze za běhu, ladění aplikace Windows Forms, musíte provést následující kroky:  
  
2.  Nastavte `jitDebugging` hodnotu `true` v `system.windows.form` části souboru machine.config nebo  *\<název aplikace >*. exe.config souboru:  
  
    ```  
    <configuration>  
        <system.windows.forms jitDebugging="true" />  
    </configuration>  
    ```  
  
3.  V aplikaci C++ Windows Form, je nutné také nastavit `DebuggableAttribute` do souboru .config nebo v kódu. Pokud je kompilovat s [/Zi](/cpp/build/reference/z7-zi-zi-debug-information-format) a bez [/Og](/cpp/build/reference/og-global-optimizations), kompilátor tento atribut nastaví za vás. Pokud chcete k ladění sestavení pro vydání není optimalizovaná, ale musíte nastavit sobě. Můžete provést přidáním následujícího řádku vám jste soubor AssemblyInfo.cpp vaší aplikace:  
  
    ```  
    [assembly:System::Diagnostics::DebuggableAttribute(true, true)];   
    ```  
  
     Další informace naleznete v tématu <xref:System.Diagnostics.DebuggableAttribute>.  
  
## <a name="a-namebkmkusingjituse-just-in-time-debugging"></a><a name="BKMK_Using_JIT">Použít ladění za běhu  
 Tato část uvádí, co se stane, když spustitelný soubor vyvolá výjimku.  
  
 Musíte mít nainstalovanou následující postup použijte sadu Visual Studio. Pokud nemáte Visual Studio, si můžete stáhnout bezplatnou [Visual Studio Community Edition](https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Community&rel=15).  
  
 Ujistěte se, že pouze za běhu ladění je [povoleno](#BKMK_Enabling).
  
 Pro účely tohoto oddílu vytočit konzolovou aplikaci C# v sadě Visual Studio, který vyvolá [NullReferenceException](http://msdn.microsoft.com/Library/658af786-d893-4114-a3c5-31c7d586056a).  
  
 Ve Visual Studiu Vytvořte konzolovou aplikaci C# (**soubor > Nový > Projekt > Visual C# > Konzolová aplikace**) s názvem **ThrowsNullException**. Další informace o vytváření projektů v sadě Visual Studio najdete v tématu [návod: vytvoření jednoduché aplikace](../ide/walkthrough-create-a-simple-application-with-visual-csharp-or-visual-basic.md).  
  
 Když na projekt se otevře v sadě Visual Studio, otevřete soubor Program.cs. Následující kód, který vytiskne řádek do konzoly a poté vyvolá NullReferenceException nahraďte metodu Main():  
  
```csharp  
static void Main(string[] args)  
{  
    Console.WriteLine("we will now throw a NullReferenceException");  
    throw new NullReferenceException("this is the exception thrown by the console app");  
}  
```  
  
> [!IMPORTANT]
>  Aby tento postup pro práci v [konfigurace verze](../debugger/how-to-set-debug-and-release-configurations.md), je potřeba vypnout [pouze můj kód](../debugger/just-my-code.md). V sadě Visual Studio, klikněte na tlačítko **nástroje > Možnosti**. V **možnosti** dialogovém okně, vyberte **ladění**. Odebrat kontrolu z **povolit volbu pouze vlastní kód**.  
  
 Sestavte řešení (v sadě Visual Studio, vyberte **sestavení > znovu sestavit řešení**). Můžete vybrat ladění nebo verze konfigurace (zvolte **ladění** pro úplné ladění prostředí). Další informace o konfiguracích sestavení najdete v tématu [Principy konfigurací sestavení](../ide/understanding-build-configurations.md).  
  
 Proces sestavení vytvoří spustitelný soubor ThrowsNullException.exe. Najdete ho ve složce, kde jste vytvořili projekt C#: **...\ThrowsNullException\ThrowsNullException\bin\Debug** nebo **...\ThrowsNullException\ThrowsNullException\bin\Release**.  
  
 Dvakrát klikněte ThrowsNullException.exe. Měli byste vidět okno příkazového řádku takto:  
  
 ![ThrowsNullExceptionConsole](../debugger/media/throwsnullexceptionconsole.png "ThrowsNullExceptionConsole")  
  
 Za několik sekund zobrazí se okno s chyba:  
  
 ![ThrowsNullExceptionError](../debugger/media/throwsnullexceptionerror.png "ThrowsNullExceptionError")  
  
 Neklikejte na **zrušit**! Za několik sekund, měli byste vidět dvě tlačítka **ladění** a **ukončení programu**. Klikněte na tlačítko **ladění**.  
  
> [!CAUTION]
>  Pokud vaše aplikace obsahuje nedůvěryhodnými, zobrazí se dialogové okno s upozorněním zabezpečení. Toto dialogové okno můžete rozhodnout, zda chcete pokračovat v ladění. Než budete pokračovat s laděním, rozhodněte, zda důvěřujete kód. Napíšete kód sami? Důvěřujete tvůrci? Pokud aplikace běží na vzdáleném počítači, můžete k rozpoznání názvu procesu? I když aplikace běží místně, který nemusí nezbytně znamenat, že může být důvěryhodný. Zvažte možnost běžícího na vašem počítači škodlivý kód. Pokud se rozhodnete, že kód Chystáte se ladění je důvěryhodný, klikněte na tlačítko **ladění**. Jinak, klikněte na tlačítko **nemáte ladění**.  
  
 **Visual Studio Debugger JIT** zobrazí se okno:  
  
 ![JustInTimeDialog](../debugger/media/justintimedialog.png "JustInTimeDialog")  
  
 V části **možné ladicí programy**, měli byste vidět, který **novou instanci třídy sady Microsoft Visual Studio <available version>**  je vybraný řádek. Pokud již není vybrána, vyberte ho.  
  
 V dolní části okna v části **chcete ladění pomocí vybrané ladicí program?**, klikněte na tlačítko **Ano**.  
  
 ThrowsNullException projekt se otevře v nové instanci sady Visual Studio, s byl zastaven na řádku, která vyvolala výjimku:  
  
 ![NullReferenceSecondInstance](../debugger/media/nullreferencesecondinstance.png "NullReferenceSecondInstance")  
  
 Můžete spustit v tomto okamžiku ladění. Pokud to byly reálné aplikaci, musíte zjistit, proč kód způsobující výjimku.  
  
## <a name="just-in-time-debugging-errors"></a>Chyby ladění za běhu  
 Pokud nevidíte dialogové okno, pokud dojde k chybě programu, může to z důvodu nastavení zasílání zpráv o chybách systému Windows ve vašem počítači. Další informace najdete v tématu [. Nastavení WER](/windows-hardware/drivers/dashboard/windows-error-reporting-getting-started).  
  
 Může se zobrazit následující chybové zprávy, které jsou přidruženy pouze za běhu ladění.  
  
-   **Nelze připojit k procesu selhávání. Zadaný program není program Windows nebo MS-DOS.**  
  
     K této chybě dojde při pokusu o připojení k proces, který běží jako jiný uživatel.  
  
     Chcete-li vyřešit tento problém, spuštění Visual Studio, otevřete **připojit k procesu** dialogové okno z **ladění** nabídce a najít procesu, kterou chcete ladit v **dostupné procesy**seznamu. Pokud neznáte název procesu, podívejte se na **Visual Studio Debugger JIT** dialogové okno a poznamenejte si ID procesu. Vyberte proces v **dostupné procesy** seznamu a klikněte na tlačítko **Attach**. V **Visual Studio Debugger JIT** dialogové okno, klikněte na tlačítko **ne** zavřete dialogové okno.  
  
-   **Ladicí program nelze spustit, protože není přihlášen žádný uživatel.**  
  
     K této chybě dojde, když těsně za běhu ladění pokusí o spuštění sady Visual Studio na počítači, kde není uživatele přihlášený ke konzole. Vzhledem k tomu, že je přihlášen žádný uživatel, není žádná relace uživatele k zobrazení pouze v době ladění dialogové okno.  
  
     Chcete-li tento problém vyřešit, přihlaste se na počítač.  
  
-   **Třída není zaregistrovaný.**  
  
     Tato chyba znamená, že ladicí program pokusil vytvořit třídu COM, která není registrované, pravděpodobně z důvodu potíží instalace.  
  
     Chcete-li tento problém vyřešit, použijte instalační disk přeinstalujte nebo opravte instalaci aplikace Visual Studio.  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Základy ladicího programu](../debugger/debugger-basics.md)   
 [V běhu, ladění, dialogové okno Možnosti](../debugger/just-in-time-debugging-options-dialog-box.md)   
 [Upozornění zabezpečení: Připojení k procesu, jehož vlastníkem je nedůvěryhodný uživatel, může být nebezpečné. Pokud následující údaje vypadají podezřele nebo si nejste jistí, k tomuto procesu se nepřipojujte.](../debugger/security-warning-attaching-to-a-process-owned-by-an-untrusted-user.md)
