---
title: "Návod: Ladění formuláře systému Windows | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], walkthroughs
- debugging managed code, Windows Forms
- debugging [Visual Studio], Windows Forms
- Attach to Process dialog box
- debugger, attaching to programs
- Attach to Process dialog box, walkthroughs
- Windows Forms, debugging
- debugging Windows Forms, walkthroughs
ms.assetid: 529db1e2-d9ea-482a-b6a0-7c543d17f114
caps.latest.revision: "28"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 02db9a01286e65f371ab4d8388102a3db4c5602e
ms.sourcegitcommit: 1e08318a8a684b21609af7a5e48b56abcc3239e6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/13/2017
---
# <a name="walkthrough-debugging-a-windows-form"></a>Návod: Ladění formuláře systému Windows
Aplikace modelu Windows Form jsou jedny nejběžnějších spravovaných aplikací. Model Windows Form vytvoří standardní aplikaci systému Windows. Tuto rekapitulaci lze dokončit pomocí jazyků Visual Basic, C# nebo C++.  
  
 Nejprve je nutné zavřít všechna otevřená řešení.  
  
### <a name="to-prepare-for-this-walkthrough"></a>Příprava pro Tento názorný postup  
  
-   Pokud již máte své řešení otevřené, zavřete je. (Na **soubor** nabídce vyberte možnost **zavřít řešení**.)  
  
## <a name="create-a-new-windows-form"></a>Vytvoření nové aplikace modelu Windows Form  
 V dalších krocích vytvoříte nový formulář aplikace modelu Windows Form.  
  
#### <a name="to-create-the-windows-form-for-this-walkthrough"></a>Vytvoření formuláře aplikace modelu Windows Form pro tuto rekapitulaci  
  
1.  Na **soubor** nabídce zvolte **nový** a klikněte na tlačítko **projektu**.  
  
     **Nový projekt** zobrazí se dialogové okno.  
  
2.  V podokně typy projektů, otevřete **jazyka Visual Basic**, **Visual C#**, nebo **Visual C++** uzlu, pak  
  
    1.  Visual Basic a Visual C#, vyberte **Windows** uzlu, pak vyberte **formulářová aplikace Windows** v **šablony** podokně.  
  
    2.  Visual C++, vyberte **CLR** uzlu, pak vyberte **formulářová aplikace Windows** v **šablony** podokně...  
  
3.  V **šablony** podokně, vyberte **aplikace Windows**.  
  
4.  V **název** pole, zadejte jedinečný název (například Walkthrough_SimpleDebug) projektu.  
  
5.  Click **OK**.  
  
     Systém Visual Studio vytvoří nový projekt a nový formulář zobrazí v Návrháři formulářů Windows Forms. Další informace najdete v tématu [Návrhář formulářů Windows](http://msdn.microsoft.com/en-us/3c3d61f8-f36c-4d41-b9c3-398376fabb15).  
  
6.  Na **zobrazení** nabídce vyberte možnost **sada nástrojů**.  
  
     Otevřete panel nástrojů. Další informace najdete v tématu [sada nástrojů](../ide/reference/toolbox.md).  
  
7.  V panelu nástrojů klikněte na **tlačítko** řízení a přetáhněte ovládací prvek na formuláři návrhovou plochu. Přetáhněte tlačítko na formulář.  
  
8.  V panelu nástrojů klikněte na **TextBox** řízení a přetáhněte ovládací prvek na formuláři návrhovou plochu. Vyřaďte **TextBox** na formuláři.  
  
9. Na návrhové ploše formuláře dvakrát klikněte na tlačítko.  
  
     Tím přejdete na stránku kódu. Kurzor by měl být umístěn v obslužné rutině události `button1_Click`.  
  
10. Do funkce `button1_Click` přidejte následující kód:  
  
    ```  
    ' Visual Basic  
    textBox1.Text = "Button was clicked!"  
  
    // C#  
    textBox1.Text = "Button was clicked!";  
  
    // C++  
    textBox1->Text = "Button was clicked!";  
    ```  
  
11. Na **sestavení** nabídce vyberte možnost **sestavit řešení**.  
  
     Projekt by se měl sestavit bez chyb.  
  
## <a name="debug-your-form"></a>Ladění formuláře  
 Nyní jste připraveni začít s laděním.  
  
#### <a name="to-debug-the-windows-form-created-for-this-walkthrough"></a>Ladění aplikace modelu Windows Form vytvořené v této rekapitulaci  
  
1.  V okně zdroje klikněte na levý okraj řádku, na který jste přidali text:  
  
    ```  
    ' Visual Basic  
    textBox1.Text = "Button was clicked!"  
  
    // C#  
    textBox1.Text = "Button was clicked!";  
  
    // C++  
    textBox1->Text = "Button was clicked!";  
    ```  
  
     Zobrazí se červená tečka a text řádku se zvýrazní červeně. Tato červená tečka představuje zarážku. Další informace najdete v tématu [zarážky](http://msdn.microsoft.com/en-us/fe4eedc1-71aa-4928-962f-0912c334d583). Při spuštění aplikace pomocí ladicího programu v tomto místě ladicí program přeruší provádění, když je tento řádek kódu dosažen. Poté lze zobrazit stav aplikace a ladit ji.  
  
    > [!NOTE]
    >  Můžete také kliknout pravým tlačítkem kterýkoli řádek kódu, přejděte na **zarážek**a potom klikněte na **vložit zarážku** přidat zarážky na daného řádku.  
  
2.  ON **ladění** nabídce zvolte **spustit**.  
  
     Aplikace modelu Windows Form se spustí.  
  
3.  Na formuláři aplikace modelu Windows Form klikněte na tlačítko, které jste přidali.  
  
     To vás v systému Visual Studio přenese na stránku kódu k řádku, na který jste nastavili zarážku. Tento řádek by měl být zvýrazněn žlutou barvou. Nyní lze zobrazit proměnné aplikace a řídit její spuštění. Aplikace nyní zastavila provádění a čeká na vaši akci.  
  
4.  Na **ladění** nabídce zvolte **Windows**, pak **sledovat**a klikněte na tlačítko **Watch1**.  
  
5.  V **Watch1** klikněte na prázdný řádek. V **název** zadejte `textBox1.Text` (Pokud používáte Visual Basic a Visual C#) nebo `textBox1->Text` (Pokud používáte C++), stiskněte klávesu ENTER.  
  
     **Watch1** okno zobrazuje hodnotu této proměnné v uvozovkách jako:  
  
    ```  
    ""  
    ```  
  
6.  Na **ladění** nabídky, zvolte **Krokovat s vnořením**.  
  
     Hodnota textBox1.Text změny v **Watch1** okna:  
  
    ```  
    Button was clicked!  
    ```  
  
7.  Na **ladění** nabídce zvolte **pokračovat** obnovit ladění vašeho programu.  
  
8.  Klikněte znovu na tlačítko na formuláři aplikace Windows Form.  
  
     Systém Visual Studio znovu přeruší spuštění.  
  
9. Klikněte na červenou tečku představující zarážku.  
  
     Tím tuto zarážku odstraníte z kódu.  
  
10. Na **ladění** nabídky, zvolte **Zastavte ladění**.  
  
## <a name="attach-to-your-windows-form-application-for-debugging"></a>Připojení k aplikaci modelu Windows Form pro ladění  
 V systému [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] lze ladicí program připojit ke spuštěnému procesu. Pokud používáte verzi Express, není tato funkce podporována.  
  
#### <a name="to-attach-to-the-windows-form-application-for-debugging"></a>Připojení k aplikaci modelu Windows Form pro ladění  
  
1.  V projektu, který jste vytvořili výše, klikněte na levý okraj řádku, který jste přidali, abyste znovu nastavili zarážku:  
  
    ```  
    ' Visual Basic  
    textBox1.Text = "Button was clicked!"  
  
    // C#  
    textBox1.Text = "Button was clicked!"  
  
    // C++  
    textBox1->Text = "Button was clicked!";  
    ```  
  
2.  Na **ladění** nabídce vyberte možnost **spustit bez ladění**.  
  
     Aplikace modelu Windows Form se spustí v systému Windows stejně, jako kdyby jste dvakrát kliknuli na její spustitelný soubor. Ladicí program není připojen.  
  
3.  Na **ladění** nabídce vyberte možnost **připojit k procesu**. (Tento příkaz je také k dispozici na **nástroje** nabídky.)  
  
     **Připojit k procesu** zobrazí se dialogové okno.  
  
4.  V **dostupné procesy** podokně, najít proces názvu (Walkthrough_SimpleDebug.exe) **proces** sloupce a klikněte na něj.  
  
5.  Klikněte **Attach** tlačítko.  
  
6.  Na formuláři Windows Form vaší aplikace klikněte na tlačítko.  
  
     Ladicí program při dosažení zarážky přeruší spuštění formuláře aplikace modelu Windows Form.  
  
## <a name="see-also"></a>Viz také  
 [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)   
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)