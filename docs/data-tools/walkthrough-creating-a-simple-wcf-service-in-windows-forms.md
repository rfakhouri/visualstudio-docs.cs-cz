---
title: 'Návod: Vytvoření jednoduché služby WCF ve Windows Forms | Microsoft Docs'
ms.custom: ''
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
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: cacd1e15d2b20c4c24056416df4f9d25ea87474e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-creating-a-simple-wcf-service-in-windows-forms"></a>Návod: Vytvoření jednoduché služby WCF ve Windows Forms
Tento návod ukazuje, jak vytvořit jednoduchou [!INCLUDE[vsindigo](../data-tools/includes/vsindigo_md.md)] služby, otestovat ji a potom k němu přístup z aplikace Windows Forms.  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## <a name="creating-the-service"></a>Vytvoření služby  
  
#### <a name="to-create-a-wcf-service"></a>Vytvoření služby WCF  
  
1.  Na **soubor** nabídky, přejděte na příkaz **nový** a pak klikněte na **projektu**.  
  
2.  V **nový projekt** dialogové okno, rozbalte seznam **jazyka Visual Basic** nebo **Visual C#** uzel a klikněte na tlačítko **WCF**, za nímž následují **WCF Služba knihovny**. Klikněte na tlačítko **OK** otevřít projekt.  
  
     ![Projekt knihovny služby WCF](../data-tools/media/wcf1.PNG "wcf1")  
  
    > [!NOTE]
    >  Tím se vytvoří pracovní služba, která můžete otestovat a získat přístup. Následující dva kroky ukazují, jak můžete upravit výchozí metodu k použití na jiný datový typ. V reálné aplikaci byste také přidat vašich vlastních funkcích ke službě.  
  
3.  ![Soubor IService1](../data-tools/media/wcf2.png "wcf2")  
  
     V **Průzkumníku**, dvakrát klikněte na IService1.vb nebo IService1.cs a vyhledejte následující řádek:  
  
     [!code-csharp[WCFWalkthrough#4](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_1.cs)]
     [!code-vb[WCFWalkthrough#4](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_1.vb)]  
  
     Změnit typ pro `value` parametr na řetězec:  
  
     [!code-csharp[WCFWalkthrough#1](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_2.cs)]
     [!code-vb[WCFWalkthrough#1](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_2.vb)]  
  
     Ve výše uvedeném kódu si poznamenejte `<OperationContract()>` nebo `[OperationContract]` atributy. Tyto atributy jsou vyžadované pro jakékoli metody vystavené službu.  
  
4.  ![Soubor Service1](../data-tools/media/wcf3.png "wcf3")  
  
     V **Průzkumníku**, dvakrát klikněte na Service1.vb nebo Service1.cs a vyhledejte následující řádek:  
  
     [!code-vb[WCFWalkthrough#5](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_3.vb)]
     [!code-csharp[WCFWalkthrough#5](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_3.cs)]  
  
     Změňte typ pro parametr hodnotu na řetězec:  
  
     [!code-csharp[WCFWalkthrough#2](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_4.cs)]
     [!code-vb[WCFWalkthrough#2](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_4.vb)]  
  
## <a name="testing-the-service"></a>Testování služby  
  
#### <a name="to-test-a-wcf-service"></a>K testování služby WCF  
  
1.  Stiskněte klávesu **F5** službu spustit. A **testovacího klienta WCF** zobrazí formulář a načte službu.  
  
2.  V **testovacího klienta WCF** formuláři, dvakrát klikněte **GetData()** metoda pod **IService1**. **GetData** karta se zobrazí.  
  
     ![GetData&#40; &#41; metoda](../data-tools/media/wcf4.png "wcf4")  
  
3.  V **požadavku** vyberte **hodnotu** pole a zadejte `Hello`.  
  
     ![Pole hodnoty](../data-tools/media/wcf5.png "wcf5")  
  
4.  Klikněte **Invoke** tlačítko. Pokud **upozornění zabezpečení** dialogové okno se zobrazí, klikněte na tlačítko **OK**. Výsledek se zobrazí v **odpovědi** pole.  
  
     ![Výsledek v odpovědi pole](../data-tools/media/wcf6.png "wcf6")  
  
5.  Na **soubor** nabídky, klikněte na tlačítko **ukončení** testovací formulář zavřete.  
  
## <a name="accessing-the-service"></a>Přístupu ke službě  
  
#### <a name="to-reference-a-wcf-service"></a>Chcete-li služby WCF  
  
1.  Na **soubor** nabídky, přejděte na příkaz **přidat** a pak klikněte na **nový projekt**.  
  
2.  V **nový projekt** dialogové okno, rozbalte seznam **jazyka Visual Basic** nebo **Visual C#** uzel a vyberte možnost **Windows**a potom vyberte **Aplikaci Windows Forms**. Klikněte na tlačítko **OK** otevřít projekt.  
  
     ![Projekt aplikace Windows Forms](../data-tools/media/wcf7.png "wcf7")  
  
3.  Klikněte pravým tlačítkem na **WindowsApplication1** a klikněte na tlačítko **přidat odkaz na službu**. **Přidat odkaz na službu** se zobrazí dialogové okno.  
  
4.  V **přidat odkaz na službu** dialogové okno, klikněte na tlačítko **Discover**.  
  
     ![Dialogové okno Přidat odkaz na službu](../data-tools/media/wcf8.png "wcf8")  
  
     **Service1** se zobrazí na **služby** podokně.  
  
5.  Klikněte na tlačítko **OK** přidat odkaz na službu.  
  
#### <a name="to-build-a-client-application"></a>K vytvoření aplikace klienta  
  
1.  V **Průzkumníku řešení**, dvakrát klikněte na **Form1.vb** nebo **Form1.cs** otevřít Návrhář formulářů Windows, pokud ještě není otevřené.  
  
2.  Z **sada nástrojů**, přetáhněte `TextBox` řízení, `Label` řízení a `Button` ovládací prvek na formuláři.  
  
     ![Přidání ovládacích prvků na formuláři](../data-tools/media/wcf9.png "wcf9")  
  
3.  Dvakrát klikněte `Button`a přidejte následující kód v `Click` obslužné rutiny události:  
  
     [!code-csharp[WCFWalkthrough#3](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_5.cs)]
     [!code-vb[WCFWalkthrough#3](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_5.vb)]  
  
4.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na **WindowsApplication1** a klikněte na tlačítko **nastavit jako spouštěný projekt**.  
  
5.  Stiskněte klávesu **F5** spustit projekt. Zadejte text a klikněte na tlačítko. Zobrazí popisek "zadali jste:" a text, který jste zadali.  
  
     ![Formulář, který zobrazuje výsledek](../data-tools/media/wcf10.png "wcf10")  
  
## <a name="see-also"></a>Viz také  
 [Služby Windows Communication Foundation a služby WCF Data Services v sadě Visual Studio](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)