---
title: 'Návod: Vytvoření jednoduché služby WCF ve Windows Forms | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
helpviewer_keywords:
- WCF, walkthrough [Visual Studio]
- WCF, Visual Studio tools for
- WCF services
- WCF services, walkthrough
ms.assetid: 5fef1a64-27a4-4f10-aa57-29023e28a2d6
caps.latest.revision: 29
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 46250ad394a2fde1e7cde6f30fab9dc6d7fb579c
ms.sourcegitcommit: 77b4ca625674658d5c5766e684fa0e2a07cad4da
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/14/2019
ms.locfileid: "65615649"
---
# <a name="walkthrough-creating-a-simple-wcf-service-in-windows-forms"></a>Návod: Vytvoření jednoduché služby WCF ve Windows Forms
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tento návod ukazuje, jak vytvořit jednoduchou [!INCLUDE[vsindigo](../includes/vsindigo-md.md)] služby, otestovat ji a pak k němu přístup z aplikace Windows Forms.

 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]

## <a name="creating-the-service"></a>Vytvoření služby

#### <a name="to-create-a-wcf-service"></a>Vytvoření služby WCF

1. Na **souboru** nabídky, přejděte k **nový** a potom klikněte na tlačítko **projektu**.

2. V **nový projekt** dialogového okna rozbalte **jazyka Visual Basic** nebo **Visual C#** uzel a klikněte na tlačítko **WCF**následovaný **WCF Knihovna služby**. Klikněte na tlačítko **OK** pro otevření projektu.

     ![Projekt knihovny služby WCF](../data-tools/media/wcf1.PNG "wcf1")

    > [!NOTE]
    > Tím se vytvoří funkční služba, která můžete otestovat a získat přístup. Následující kroky ukazují, jak je možné změnit výchozí metodu chcete použít jiný datový typ. V reálné aplikaci byste také přidat vašich vlastních funkcích ve službě.

3. ![Soubor IService1](../data-tools/media/wcf2.png "wcf2")

     V **Průzkumníka řešení**, dvakrát klikněte na panel IService1.vb nebo IService1.cs a vyhledejte následující řádek:

     [!code-csharp[WCFWalkthrough#4](../snippets/csharp/VS_Snippets_VBCSharp/wcfwalkthrough/cs/iservice1_2.cs#4)]
     [!code-vb[WCFWalkthrough#4](../snippets/visualbasic/VS_Snippets_VBCSharp/wcfwalkthrough/vb/iservice1_2.vb#4)]

     Změnit typ `value` parametr `String`:

     [!code-csharp[WCFWalkthrough#1](../snippets/csharp/VS_Snippets_VBCSharp/wcfwalkthrough/cs/iservice1.cs#1)]
     [!code-vb[WCFWalkthrough#1](../snippets/visualbasic/VS_Snippets_VBCSharp/wcfwalkthrough/vb/iservice1.vb#1)]

     Ve výše uvedeném kódu, Všimněte si, `<OperationContract()>` nebo `[OperationContract]` atributy. Tyto atributy jsou požadovány pro libovolnou metodu určeného službou.

4. ![Soubor Service1](../data-tools/media/wcf3.png "wcf3")

     V **Průzkumníka řešení**, dvakrát klikněte na panel Service1.vb nebo Service1.cs a vyhledejte následující řádek:

     [!code-csharp[WCFWalkthrough#5](../snippets/csharp/VS_Snippets_VBCSharp/wcfwalkthrough/cs/service1_2.cs#5)]
     [!code-vb[WCFWalkthrough#5](../snippets/visualbasic/VS_Snippets_VBCSharp/wcfwalkthrough/vb/service1_2.vb#5)]

     Změnit typ pro parametr hodnotu `String`:

     [!code-csharp[WCFWalkthrough#2](../snippets/csharp/VS_Snippets_VBCSharp/wcfwalkthrough/cs/service1.cs#2)]
     [!code-vb[WCFWalkthrough#2](../snippets/visualbasic/VS_Snippets_VBCSharp/wcfwalkthrough/vb/service1.vb#2)]

## <a name="testing-the-service"></a>Testování služby

#### <a name="to-test-a-wcf-service"></a>K otestování služby WCF

1. Stisknutím klávesy **F5** ke spuštění služby. A **testovací klient WCF** zobrazí formulář a načte službu.

2. V **testovací klient WCF** formuláře, dvakrát klikněte **GetData()** metody **IService1**. **GetData** kartě se zobrazí.

     ![GetData&#40; &#41; metoda](../data-tools/media/wcf4.png "wcf4")

3. V **žádosti** vyberte **hodnotu** pole a zadejte `Hello`.

     ![Pole hodnoty](../data-tools/media/wcf5.png "wcf5")

4. Klikněte na tlačítko **Invoke** tlačítko. Pokud **upozornění zabezpečení** dialogové okno se zobrazí, klikněte na tlačítko **OK**. Výsledek se zobrazí v **odpovědi** pole.

     ![Výsledek v poli odpovědi](../data-tools/media/wcf6.png "wcf6")

5. Na **souboru** nabídky, klikněte na tlačítko **ukončovací** testovací formulář zavřete.

## <a name="accessing-the-service"></a>Přístupu ke službě

#### <a name="to-reference-a-wcf-service"></a>K odkazu na službu WCF

1. Na **souboru** nabídky, přejděte k **přidat** a potom klikněte na tlačítko **nový projekt**.

2. V **nový projekt** dialogového okna rozbalte **jazyka Visual Basic** nebo **Visual C#** uzel a vyberte možnost **Windows**a pak vyberte **Aplikaci Windows Forms**. Klikněte na tlačítko **OK** pro otevření projektu.

     ![Projekt aplikace Windows Forms](../data-tools/media/wcf7.png "wcf7")

3. Klikněte pravým tlačítkem na **WindowsApplication1** a klikněte na tlačítko **přidat odkaz na službu**. **Přidat odkaz na službu** se zobrazí dialogové okno.

4. V **přidat odkaz na službu** dialogové okno, klikněte na tlačítko **Discover**.

     ![V dialogovém okně Přidat odkaz na službu](../data-tools/media/wcf8.png "wcf8")

     **Service1** se zobrazí v **služby** podokně.

5. Klikněte na tlačítko **OK** přidáte odkaz na službu.

#### <a name="to-build-a-client-application"></a>K vytvoření klientské aplikace

1. V **Průzkumníka řešení**, dvakrát klikněte na panel **Form1.vb** nebo **Form1.cs** otevřete návrhář formulářů Windows, pokud ještě není otevřený.

2. Z **nástrojů**, přetáhněte `TextBox` ovládací prvek, `Label` ovládacího prvku a `Button` ovládací prvek na formuláři.

     ![Přidání ovládacích prvků na formuláři](../data-tools/media/wcf9.png "wcf9")

3. Dvakrát klikněte `Button`a přidejte následující kód `Click` obslužné rutiny události:

     [!code-csharp[WCFWalkthrough#3](../snippets/csharp/VS_Snippets_VBCSharp/wcfwalkthrough/cs/form1.cs#3)]
     [!code-vb[WCFWalkthrough#3](../snippets/visualbasic/VS_Snippets_VBCSharp/wcfwalkthrough/vb/form1.vb#3)]

4. V **Průzkumníka řešení**, klikněte pravým tlačítkem na **WindowsApplication1** a klikněte na tlačítko **nastavit jako spouštěný projekt**.

5. Stisknutím klávesy **F5** spusťte projekt. Zadejte nějaký text a klikněte na tlačítko. Popisek se zobrazí "zadali jste:" a text, který jste zadali.

     ![Formulář, který zobrazuje výsledek](../data-tools/media/wcf10.png "wcf10")

## <a name="see-also"></a>Viz také
 [Služby Windows Communication Foundation a služby WCF Data Services v sadě Visual Studio](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)
