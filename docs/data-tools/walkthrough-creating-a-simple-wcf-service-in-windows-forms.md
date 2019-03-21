---
title: 'Návod: Vytvoření jednoduché služby WCF ve Windows Forms'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- WCF, walkthrough [Visual Studio]
- WCF, Visual Studio tools for
- WCF services
- WCF services, walkthrough
ms.assetid: 5fef1a64-27a4-4f10-aa57-29023e28a2d6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 97bbf8212caf87f28849df15d350811579f22ccd
ms.sourcegitcommit: 3d37c2460584f6c61769be70ef29c1a67397cf14
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/21/2019
ms.locfileid: "58325224"
---
# <a name="walkthrough-create-a-simple-wcf-service-in-windows-forms"></a>Návod: Vytvoření jednoduché služby WCF v modelu Windows Forms

Tento návod ukazuje, jak vytvořit jednoduchou službu Windows Communication Foundation (WCF), otestovat ji a pak k němu přístup z aplikace Windows Forms.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="create-a-service"></a>Vytvoření služby

1. Otevřít Visual Studio.

::: moniker range="vs-2017"

2. Na **souboru** nabídce zvolte **nový** > **projektu**.

3. V **nový projekt** dialogového okna rozbalte **jazyka Visual Basic** nebo **Visual C#**  uzlu a zvolte **WCF**následovaný **Knihovny služby WCF**.

4. Klikněte na tlačítko **OK** pro vytvoření projektu.

   ![Projekt knihovny služby WCF](../data-tools/media/wcf1.png)

::: moniker-end

::: moniker range=">=vs-2019"

2. V okně start zvolte **vytvořte nový projekt**.

3. Typ **knihovny služby wcf** do vyhledávacího pole na **vytvořte nový projekt** stránky. Vyberte buď C# nebo šablony jazyka Visual Basic pro **knihovny služby WCF**a potom klikněte na tlačítko **Další**.

   ![Vytvořit nový projekt knihovny služby WCF ve Visual Studio 2019](media/vs-2019/create-new-wcf-service-library.png)

   > [!TIP]
   > Pokud nevidíte žádné šablony, budete muset nainstalovat **Windows Communication Foundation** komponentu sady Visual Studio. Zvolte **nainstalovat další nástroje a funkce** otevřít instalační program sady Visual Studio. Zvolte **jednotlivé komponenty** kartu, přejděte dolů k položce **vývojových aktivit**a pak vyberte **Windows Communication Foundation**. Klikněte na tlačítko **upravit**.

4. Na **konfigurovat nový projekt** klikněte na **vytvořit**.

::: moniker-end

   > [!NOTE]
   > Tím se vytvoří funkční služba, která můžete otestovat a získat přístup. Následující kroky ukazují, jak je možné změnit výchozí metodu chcete použít jiný datový typ. V reálné aplikaci byste také přidat vašich vlastních funkcích ve službě.

5. V **Průzkumníka řešení**, dvakrát klikněte na panel **IService1.vb** nebo **IService1.cs**.

   ![Soubor IService1](../data-tools/media/wcf2.png)

   Vyhledejte následující řádek:

   [!code-csharp[WCFWalkthrough#4](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_1.cs)]
   [!code-vb[WCFWalkthrough#4](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_1.vb)]

   Změnit typ `value` parametr na řetězec:

   [!code-csharp[WCFWalkthrough#1](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_2.cs)]
   [!code-vb[WCFWalkthrough#1](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_2.vb)]

   Ve výše uvedeném kódu, Všimněte si, `<OperationContract()>` nebo `[OperationContract]` atributy. Tyto atributy jsou požadovány pro libovolnou metodu určeného službou.

6. V **Průzkumníka řešení**, dvakrát klikněte na panel **Service1.vb** nebo **Service1.cs**.

   ![Soubor Service1](../data-tools/media/wcf3.png)

   Vyhledejte následující řádek:

   [!code-vb[WCFWalkthrough#5](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_3.vb)]
   [!code-csharp[WCFWalkthrough#5](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_3.cs)]

   Změnit typ `value` parametr na řetězec:

   [!code-csharp[WCFWalkthrough#2](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_4.cs)]
   [!code-vb[WCFWalkthrough#2](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_4.vb)]

## <a name="test-the-service"></a>Testování služby

1. Stisknutím klávesy **F5** ke spuštění služby. A **testovací klient WCF** formulář se zobrazí a načte službu.

2. V **testovací klient WCF** formuláře, dvakrát klikněte **GetData()** metody **IService1**. **GetData** se zobrazí karta.

     ![GetData&#40; &#41; – metoda](../data-tools/media/wcf4.png)

3. V **žádosti** vyberte **hodnotu** pole a zadejte `Hello`.

     ![Pole hodnoty](../data-tools/media/wcf5.png)

4. Klikněte na tlačítko **Invoke** tlačítko. Pokud **upozornění zabezpečení** dialogové okno se zobrazí, klikněte na tlačítko **OK**. Výsledek se zobrazí v **odpovědi** pole.

     ![Výsledek v poli odpovědi](../data-tools/media/wcf6.png)

5. Na **souboru** nabídky, klikněte na tlačítko **ukončovací** testovací formulář zavřete.

## <a name="access-the-service"></a>Přístup ke službě

### <a name="reference-the-wcf-service"></a>Odkaz na službu WCF

1. Na **souboru** nabídky, přejděte k **přidat** a potom klikněte na tlačítko **nový projekt**.

2. V **nový projekt** dialogového okna rozbalte **jazyka Visual Basic** nebo **Visual C#** uzlu, vyberte **Windows**a pak vyberte  **Aplikaci Windows Forms**. Klikněte na tlačítko **OK** pro otevření projektu.

     ![Projekt aplikace Windows Forms](../data-tools/media/wcf7.png)

3. Klikněte pravým tlačítkem na **WindowsApplication1** a klikněte na tlačítko **přidat odkaz na službu**. **Přidat odkaz na službu** zobrazí se dialogové okno.

4. V **přidat odkaz na službu** dialogové okno, klikněte na tlačítko **Discover**.

     ![V dialogovém okně Přidat odkaz na službu](../data-tools/media/wcf8.png)

     **Service1** zobrazí **služby** podokně.

5. Klikněte na tlačítko **OK** přidáte odkaz na službu.

### <a name="build-a-client-application"></a>Sestavení klientské aplikace

1. V **Průzkumníka řešení**, dvakrát klikněte na panel **Form1.vb** nebo **Form1.cs** otevřete návrhář formulářů Windows, pokud ještě není otevřený.

2. Z **nástrojů**, přetáhněte `TextBox` ovládací prvek, `Label` ovládacího prvku a `Button` ovládací prvek na formuláři.

     ![Přidání ovládacích prvků do formuláře](../data-tools/media/wcf9.png)

3. Dvakrát klikněte `Button`a přidejte následující kód `Click` obslužné rutiny události:

     [!code-csharp[WCFWalkthrough#3](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_5.cs)]
     [!code-vb[WCFWalkthrough#3](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_5.vb)]

4. V **Průzkumníka řešení**, klikněte pravým tlačítkem na **WindowsApplication1** a klikněte na tlačítko **nastavit jako spouštěný projekt**.

5. Stisknutím klávesy **F5** spusťte projekt. Zadejte nějaký text a klikněte na tlačítko. Popisek zobrazí "zadali jste:" a zobrazí text, kterou jste zadali.

     ![Formulář, který zobrazuje výsledek](../data-tools/media/wcf10.png)

## <a name="see-also"></a>Viz také:

- [Služby Windows Communication Foundation a služby WCF Data Services v sadě Visual Studio](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)