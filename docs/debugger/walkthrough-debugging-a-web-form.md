---
title: 'Návod: Ladění webového formuláře | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Web pages [.NET Framework], debugging
- Web sites [.NET Framework], debugging
- ASP.NET, debugging Web applications
- Web applications [.NET Framework], debugging
- ASP.NET Web sites, debugging
- ASP.NET Web pages, debugging
- debugging ASP.NET Web applications, Web Forms
- debugging [Visual Studio], Web Forms
ms.assetid: e2b4fa14-8f5b-444d-a903-54070b784bd4
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fe3b8333f116ea5606a354dd9d0f88f111077a1b
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2018
ms.locfileid: "37057171"
---
# <a name="walkthrough-debugging-a-web-form"></a>Návod: Ladění webového formuláře
Kroky v tomto návodu ukazují, jak k ladění [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webovou aplikaci, také známé jako webového formuláře. Ukazuje, jak spustit a zastavit provádění, nastavit zarážky a zkontrolujte proměnné v **sledovat** okno.  
  
> [!NOTE]
>  Pro dokončení tohoto návodu, musíte mít oprávnění správce na počítači serveru. Ve výchozím nastavení [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] procesu, aspnet_wp.exe nebo w3wp.exe, běží jako [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] procesu. Chcete-li ladit [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)], musí mít oprávnění správce na počítači kde [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] ho spouští. Další informace najdete v tématu [požadavky na systém](../debugger/aspnet-debugging-system-requirements.md).  
  
 Dialogová okna a příkazy nabídky, které vidíte, se může lišit od těch popsaných v nápovědě, v závislosti na aktivním nastavení nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
### <a name="to-create-the-web-form"></a>Vytvoření webové formuláře  
  
1.  Pokud již máte řešení otevřené, zavřete ji.  
  
2.  Na **soubor** nabídky, klikněte na tlačítko **nový**a potom klikněte na **webu**.  
  
     **Nový web** zobrazí se dialogové okno.  
  
3.  V **šablony** podokně klikněte na tlačítko **webové stránky ASP.NET**.  
  
4.  Na **umístění** řádek, klikněte na tlačítko **HTTP** ze seznamu a do textového pole zadejte **http://localhost/WebSite**.  
  
5.  V **jazyk** seznamu, klikněte na tlačítko **Visual C#** nebo **jazyka Visual Basic**.  
  
6.  Klikněte na tlačítko **OK**.  
  
     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Vytvoří nový projekt a zobrazí výchozí zdrojový kód HTML. Také vytvoří nový virtuální adresář s názvem **webu** pod **Default Web Site** ve službě IIS.  
  
7.  Klikněte **návrhu** karta na dolní okraj.  
  
8.  Klikněte **sada nástrojů** kartě na levým okrajem, nebo ho vyberte v **zobrazení** nabídky.  
  
     **Sada nástrojů** otevře.  
  
9. V **sada nástrojů**, klikněte na tlačítko **tlačítko** řízení a přidejte ji do hlavní návrhové ploše Default.aspx.  
  
10. V **sada nástrojů**, klikněte na tlačítko **Textbox** řízení a přetáhněte ovládací prvek hlavní návrhovou plochu, Default.aspx.  
  
11. Dvakrát klikněte na tlačítko řízení, kterou jste přetáhli.  
  
     Tím přejdete na stránku kód: Default.aspx.cs pro C# nebo Default.aspx.vb pro [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]. Kurzor by měla být ve funkci `Button1_Click`.  
  
12. V `Button1_Click` fungovat, přidejte následující kód:  
  
    ```vb  
    TextBox1.Text = "Button was clicked!"
    ```  
  
    ```csharp
    TextBox1.Text = "Button was clicked!";  
    ```  
  
13. Na **sestavení** nabídky, klikněte na tlačítko **sestavit řešení**.  
  
     Projekt má sestavit bez chyb.  
  
     Nyní jste připraveni spustit ladění.  
  
### <a name="to-debug-the-web-form"></a>K ladění webového formuláře  
  
1.  V okně Default.aspx.cs nebo Default.aspx.vb klikněte levým okrajem na stejném řádku jako text, který jste přidali:  
  
    ```vb  
    TextBox1.Text = "Button was clicked!"
    ```  

    ```csharp  
    textBox1.Text = "Button was clicked!";  
    ```  
  
     Zobrazí se červená tečka a text řádku se zvýrazní červeně. Tato červená tečka představuje zarážku. Při spuštění aplikace pomocí ladicího programu v tomto místě ladicí program přeruší provádění, když je tento řádek kódu dosažen. Poté lze zobrazit stav aplikace a ladit ji. Další informace najdete v tématu [zarážky](http://msdn.microsoft.com/en-us/fe4eedc1-71aa-4928-962f-0912c334d583).  
  
2.  Na **ladění** nabídky, klikněte na tlačítko **spustit ladění**.  
  
3.  **Ladění není povoleno** zobrazí se dialogové okno. Vyberte **upravit soubor Web.config, který chcete povolit ladění** a klikněte na **OK**.  
  
     Internet Explorer spustí a zobrazí stránku, která právě určená.  
  
4.  V aplikaci Internet Explorer klikněte na tlačítko.  
  
     V [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], tím přejdete na řádek kde nastavíte vaší zarážce znaková stránka Default.aspx.cs nebo Default.aspx.vb. Tento řádek by měl být zvýrazněn žlutou barvou. Nyní lze zobrazit proměnné aplikace a řídit její spuštění. Vaše aplikace přestane provádění a čeká příkaz od vás.  
  
5.  Na **ladění** nabídky, klikněte na tlačítko **Windows**, pak klikněte na tlačítko **sledovat**a potom klikněte na **Watch1**.  
  
6.  V **sledovat** zadejte **TextBox1.Text**.  
  
     **Sledovat** v okně se zobrazí hodnota proměnné `TextBox1.Text`:  
  
    '""' 
  
7.  Na **ladění** nabídky, klikněte na tlačítko **Krokovat s přeskočením**.  
  
     Hodnota `TextBox1.Text` změn v **sledovat** okno ke čtení:  
  
    `"Button was clicked!"`  
  
8.  Na **ladění** nabídky, klikněte na tlačítko **pokračovat**.  
  
9. V aplikaci Internet Explorer klikněte na tlačítko znovu.  
  
     Provádění zastaví u zarážky znovu.  
  
10. V okně Default.aspx.cs nebo Default.aspx.vb klikněte na červenou tečku na levém okraji.  
  
     Touto akcí odeberete bod přerušení.  
  
11. Na **ladění** nabídky, klikněte na tlačítko **Zastavte ladění**.  
  
### <a name="to-attach-to-the-web-form-for-debugging"></a>Pro připojení k webového formuláře pro ladění  
  
1.  V systému [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] lze ladicí program připojit ke spuštěnému procesu. Pro co nejúčinnější ladění kompilace jako ladicí verze spustitelného souboru s soubory symbolů (PDB).  
  
2.  V okně Default.aspx.cs nebo Default.aspx.vb klikněte na levém okraji se znovu nastavit zarážky na řádek, který jste přidali:  
  
    ```vb  
    TextBox1.Text = "Button was clicked!"
    ```
  
    ```csharp  
    textBox1.Text = "Button was clicked!";  
    ```  
  
3.  Na **ladění** nabídky, klikněte na tlačítko **spustit bez ladění**.  
  
     Spustí webový formulář pro spuštění v aplikaci Internet Explorer, ale není připojen ladicí program.  
  
4.  Připojit k [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] procesu. Další informace najdete v tématu [ladění nasazené webové aplikace](../debugger/debugging-deployed-web-applications.md).  
  
5.  V aplikaci Internet Explorer klikněte na tlačítko ve formuláři.  
  
     V [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], by měl dosáhl zarážka v Default.aspx.cs, Default.aspx.vb nebo Default.aspx.  
  
6.  Po dokončení ladění na **ladění** nabídky, klikněte na tlačítko **Zastavte ladění**.  
  
## <a name="see-also"></a>Viz také  
 [Ladění aplikací ASP.NET](../debugger/how-to-enable-debugging-for-aspnet-applications.md)