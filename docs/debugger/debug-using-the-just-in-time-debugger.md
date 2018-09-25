---
title: Ladění pomocí ladicího programu za běhu | Dokumentace Microsoftu
ms.custom: ''
ms.date: 09/24/18
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
ms.openlocfilehash: 7a2e6cfbd6d26d575bab5d7592f320779ffd8888
ms.sourcegitcommit: 000cdd1e95dd02e99a7c7c1a34c2f8fba6a632af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/25/2018
ms.locfileid: "47168393"
---
# <a name="debug-using-the-just-in-time-debugger-in-visual-studio"></a>Ladění pomocí ladicího programu za běhu v sadě Visual Studio
Ladění za běhu spustí sadu Visual Studio automaticky dojde k výjimce nebo selhání v aplikaci, která běží mimo sadu Visual Studio. To umožňuje testovat aplikaci, když není spuštěná sada Visual Studio a začít ladění pomocí sady Visual Studio, když dojde k potížím.

Ladění Just-In-Time funguje pro aplikace klasické pracovní plochy Windows. Nefunguje pro univerzální aplikace pro Windows a nefunguje pro spravovaný kód, který je hostován v nativní aplikaci, například pro Vizualizátory.

> [!TIP]
> Pokud chcete pouze vědět, jak reagovat na Just-in-Time dialogové okno ladicího programu, najdete v článku [v tomto tématu](../debugger/just-in-time-debugging-in-visual-studio.md).

##  <a name="BKMK_Enabling"></a> Povolení nebo zakázání Just-In-Time ladění
Můžete povolit nebo zakázat Just-In-Time ladění ze sady Visual Studio **nástroje > Možnosti** dialogové okno.

#### <a name="to-enable-or-disable-just-in-time-debugging"></a>Povolení nebo zakázání Just-In-Time ladění

1.  Otevřít Visual Studio s oprávněními správce (klikněte pravým tlačítkem a zvolte **spustit jako správce**).

    Povolení nebo zakázání Just-In-Time ladění nastaví klíč registru, a chcete-li změnit tento klíč může být nutná oprávnění správce.

2. Na **nástroje** nabídky, klikněte na tlačítko **možnosti**.

2.  V **možnosti** dialogového okna rozbalte **ladění** uzlu.

3.  V **ladění** uzlu, vyberte **Just-In-Time**.

    ![Povolení nebo zakázání ladění JIT](../debugger/media/dbg-jit-enable-or-disable.png "povolení nebo zakázání ladění za běhu")

4.  V **povolit ladění za běhu tyto typy kódu** pole, zaškrtněte nebo zrušte zaškrtnutí odpovídajících typů programů: **spravované**, **nativní**, nebo **skript**.

5.  Klikněte na tlačítko **OK**.

    Pokud povolíte Just-in-Time ladicího programu, ale nevidíte ji na selhání aplikace nebo výjimky, naleznete v tématu [Just-In-Time ladění chyb](#jit_errors).

Ladění Just-In-Time může být stále povoleno i v případě, že ve vašem počítači je již nainstalované sady Visual Studio. Pokud není nainstalována sada Visual Studio, už se nedá vypnout Just-In-Time ladění ze sady Visual Studio **možnosti** dialogové okno. V takovém případě můžete zakázat Just-In-Time ladění pomocí úpravy registru Windows.

#### <a name="to-disable-just-in-time-debugging-by-editing-the-registry"></a>Chcete-li zakázat Just-In-Time ladění pomocí úpravy registru

1.  Na **Start** nabídky, vyhledejte a spusťte `regedit.exe`

2.  V **Editor registru** okna, vyhledejte a odstraňte následující položky registru:

    -   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AeDebug\Debugger

    -   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework\DbgManagedDebugger

    ![Klíč registru JIT](../debugger/media/dbg-jit-registry.png "klíč registru JIT")

3.  Pokud počítač používá 64bitový operační systém, odstraňte také následující položky registru:

    -   HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows NT\CurrentVersion\AeDebug\Debugger

    -   HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\. NETFramework\DbgManagedDebugger

4.  Je třeba dbát na náhodnému odstranění nebo změně jiných klíčů registru.

5.  Zavřít **Editor registru** okna.

#### <a name="to-enable-just-in-time-debugging-of-a-windows-form"></a>Chcete-li povolit Just-In-Time ladění formuláře Windows

1.  Ve výchozím nastavení mají aplikace Windows Forms obslužnou rutinu výjimky nejvyšší úrovně, která umožňuje program nadále spouštět, pokud jej lze obnovit. Například pokud aplikace Windows Forms vyvolá neošetřenou výjimku, zobrazí se dialogové okno vypadat asi takto:

     ![WindowsFormsUnhandledException](../debugger/media/windowsformsunhandledexception.png "WindowsFormsUnhandledException")

     K povolení Just-In-Time ladění aplikace modelu Windows Forms, je třeba provést následující kroky:

2.  Nastavte `jitDebugging` hodnota, která se `true` v `system.windows.form` část souboru machine.config nebo  *\<název_aplikace >*. exe.config souboru:

    ```xml
    <configuration>
        <system.windows.forms jitDebugging="true" />
    </configuration>
    ```

3.  V aplikaci C++ formuláře Windows, musíte taky nastavit `DebuggableAttribute` v souboru .config nebo ve vašem kódu. Pokud kompilujete s [/zi](/cpp/build/reference/z7-zi-zi-debug-information-format) a bez [/og](/cpp/build/reference/og-global-optimizations), kompilátor nastaví tento atribut za vás. Pokud chcete ladit neoptimalizované verzi sestavení, ale musíte nastavit sami. Můžete to udělat tak, že přidáte následující řádek, který jste už souboru AssemblyInfo.cpp aplikace:

    ```cpp
    [assembly:System::Diagnostics::DebuggableAttribute(true, true)];
    ```

     Další informace naleznete v tématu <xref:System.Diagnostics.DebuggableAttribute>.

## <a name="a-namebkmkusingjituse-just-in-time-debugging"></a><a name="BKMK_Using_JIT">Použijte ladění Just-In-Time
 Tato část popisuje, co se stane, když se vyvolá výjimku, spustitelný soubor.

 Musíte mít Visual Studio nainstalovali postupovat podle následujících kroků. Pokud nemáte Visual Studio, si můžete stáhnout bezplatnou [Visual Studio Community Edition](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=Community&rel=15).

 Ujistěte se, že Just-In-Time je ladění [povolené](#BKMK_Enabling).

 Pro účely tohoto oddílu uděláme konzolovou aplikaci C# v sadě Visual Studio, který vyvolá [NullReferenceException](/dotnet/api/system.nullreferenceexception).

 Ve Visual Studiu Vytvořte konzolovou aplikaci C# (**soubor > Nový > Projekt > Visual C# > Konzolová aplikace**) s názvem **ThrowsNullException**. Další informace o vytváření projektů v sadě Visual Studio najdete v tématu [návod: vytvoření jednoduché aplikace](../ide/walkthrough-create-a-simple-application-with-visual-csharp-or-visual-basic.md).

 Po otevření projektu v sadě Visual Studio otevřete soubor Program.cs. Nahraďte následující kód, který vytiskne řádek ke konzole a potom vyvolá NullReferenceException metodu Main():

```csharp
static void Main(string[] args)
{
    Console.WriteLine("we will now throw a NullReferenceException");
    throw new NullReferenceException("this is the exception thrown by the console app");
}
```

> [!IMPORTANT]
>  Aby se tento postup provést [konfiguraci vydané verze](../debugger/how-to-set-debug-and-release-configurations.md), musí si vypnout [pouze můj kód](../debugger/just-my-code.md). V sadě Visual Studio, klikněte na tlačítko **nástroje > Možnosti**. V **možnosti** dialogového okna, vyberte **ladění**. Zrušte zaškrtnutí z **povolit volbu pouze vlastní kód**.

 Sestavte řešení (v sadě Visual Studio, zvolte **sestavení > znovu sestavit řešení**). Můžete také ladit nebo konfiguraci vydané verze (zvolte **ladění** úplného ladicího prostředí). Další informace o konfiguracích sestavení naleznete v tématu [Principy konfigurací sestavení](../ide/understanding-build-configurations.md).

 Proces sestavení vytvoří spustitelný soubor ThrowsNullException.exe. Najdete ho ve složce, ve které jste vytvořili projekt C#: **...\ThrowsNullException\ThrowsNullException\bin\Debug** nebo **...\ThrowsNullException\ThrowsNullException\bin\Release**.

 Dvakrát klikněte ThrowsNullException.exe. Měli byste vidět okno příkazového řádku takto:

 ![ThrowsNullExceptionConsole](../debugger/media/throwsnullexceptionconsole.png "ThrowsNullExceptionConsole")

 Za několik sekund zobrazí se okno aplikace Chyba:

 ![ThrowsNullExceptionError](../debugger/media/throwsnullexceptionerror.png "ThrowsNullExceptionError")

 Neklikejte na **zrušit**! Za několik sekund, měli byste vidět dvě tlačítka **ladění** a **ukončit program**. Klikněte na tlačítko **ladění**.

> [!CAUTION]
>  Pokud vaše aplikace obsahuje nedůvěryhodný kód, zobrazí se dialogové okno s upozorněním zabezpečení. Toto dialogové okno umožňuje rozhodnout, jestli chcete pokračovat v ladění. Než budete pokračovat s laděním, rozhodněte, zda kódu důvěřujete. Napsali jste kód sami? Důvěřujete kodéru? Pokud aplikace běží na vzdáleném počítači, poznáváte název procesu? I v případě, že aplikace běží místně, který nemusí nutně znamenat, že jí lze důvěřovat. Zvažte možnost škodlivý kód spuštěný ve vašem počítači. Pokud se rozhodnete, že kód Chystáte se ladit, je důvěryhodný, klikněte na tlačítko **ladění**. V opačném případě klikněte na tlačítko **Neladit**.

 **Ladicí program za běhu sady Visual Studio** okno se zobrazí:

 ![JustInTimeDialog](../debugger/media/justintimedialog.png "JustInTimeDialog")

 V části **možné ladící programy**, měli byste vidět, který **novou instanci sady Microsoft Visual Studio <available version>**  vybraný řádek. Pokud již není vybraná, vyberte ji.

 V dolní části okna v části **chcete ladit pomocí vybraný ladicí program?**, klikněte na tlačítko **Ano**.

 ThrowsNullException projekt otevře v nové instanci sady Visual Studio, s provádění zastaveno na řádku, která vyvolala výjimku:

 ![NullReferenceSecondInstance](../debugger/media/nullreferencesecondinstance.png "NullReferenceSecondInstance")

 V tomto okamžiku ladění lze spustit. Pokud to aplikace skutečný, je třeba zjistit, proč kód způsobující výjimku.

## <a name="jit_errors"></a> Chyby ladění Just-In-Time
 Pokud se nezobrazí dialogové okno, když dojde k chybě programu a potřebovat k povolení této funkce, to může být z důvodu nastavení zasílání zpráv o chybách Windows ve vašem počítači. Ujistěte se, že chcete přidat **zakázané** hodnota, která se následující klíče registru a nastavte hodnotu na 1:

* HKLM\Software\Microsoft\Windows\Windows zasílání zpráv o chybách
* HKLM\Software\WOW6432Node\Microsoft\Windows\Windows zasílání zpráv o chybách
 
Další informace o těchto nastaveních najdete v tématu [. Nastavení zasílání](https://docs.microsoft.com/windows/desktop/wer/wer-settings).

Kromě toho může se zobrazit následující chybové zprávy, které jsou spojeny s Just-In-Time ladění.

- **Nelze se připojit k havarujícímu procesu. Uvedený program není program Windows nebo MS-DOS.**

    K této chybě dochází, když se pokusíte připojit k procesu spuštěnému jako jiný uživatel.

    Chcete-li tento problém vyřešit, spusťte aplikaci Visual Studio, otevřete **připojit k procesu** dialogové **ladění** nabídky a najděte proces, který chcete ladit v **procesy k dispozici**seznamu. Pokud neznáte název procesu, podívejte se na **ladicí program za běhu sady Visual Studio** dialogové okno a poznamenejte si ID procesu. Vyberte proces v **procesy k dispozici** seznamu a klikněte na tlačítko **připojit**. V **ladicí program za běhu sady Visual Studio** dialogového okna, klikněte na tlačítko **ne** zavřete dialogové okno.

- **Ladicí program nelze spustit, protože není přihlášen žádný uživatel.**

    Tato chyba nastane, pokud Just-In-Time ladění pokusí o spuštění sady Visual Studio na počítači tam, kde neexistuje žádný uživatel přihlášený ke konzole. Protože je přihlášen žádný uživatel, neexistuje žádná uživatelská relace k zobrazení Just-In-Time ladění, dialogové okno.

    Chcete-li tento problém vyřešit, přihlaste se do počítače.

- **Třída není zaregistrována.**

    Tato chyba označuje, že ladicí program se pokusil vytvořit třídu COM, která není registrována, pravděpodobně z důvodu potíží při instalaci.

    Chcete-li tento problém vyřešit, použijte instalační disk a přeinstalujte nebo opravte instalaci sady Visual Studio.

## <a name="see-also"></a>Viz také
 [Zabezpečení ladicího programu](../debugger/debugger-security.md) [základy ladicího programu](../debugger/getting-started-with-the-debugger.md) [Just-In-Time, ladění, dialogové okno Možnosti](../debugger/just-in-time-debugging-options-dialog-box.md) [upozornění zabezpečení: připojení k procesu vlastněnému nedůvěryhodným uživatelským může být nebezpečné. Pokud následující údaje vypadají podezřele nebo si nejste jistí, k tomuto procesu se nepřipojujte.](../debugger/security-warning-attaching-to-a-process-owned-by-an-untrusted-user.md)
