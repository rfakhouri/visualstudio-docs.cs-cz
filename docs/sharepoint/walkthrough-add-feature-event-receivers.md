---
title: 'Návod: Přidání přijímačů událostí funkce | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, advanced packaging tools
- SharePoint development in Visual Studio, event receivers
- SharePoint development in Visual Studio, feature event receivers
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: cda3967d0fc95fdd8f28503f209a5f2208d07031
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-add-feature-event-receivers"></a>Návod: Přidání přijímačů událostí funkce
  Metody, které se spouští při jedné z následujících událostí související s funkcí ve službě SharePoint jsou přijímačů událostí funkce:  
  
-   Instalace funkce.  
  
-   Funkce je aktivována.  
  
-   Funkce je deaktivována.  
  
-   Funkce se odebere.  
  
 Tento návod ukazuje, jak přidat přijímače událostí funkcí v projektu služby SharePoint. Ukazuje následující úlohy:  
  
-   Vytváření prázdného projektu s příjemce událostí funkce.  
  
-   Zpracování **FeatureDeactivating** metoda.  
  
-   Přidání oznámení do seznamu oznámení pomocí objektový model projektu služby SharePoint.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   Podporované edice systému Microsoft Windows a služby SharePoint. Další informace najdete v tématu [požadavky pro vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio.  
  
## <a name="creating-a-feature-event-receiver-project"></a>Vytvoření projektu příjemce událostí funkce  
 Nejprve vytvořte projekt tak, aby obsahovala příjemce událostí funkce.  
  
#### <a name="to-create-a-project-with-a-feature-event-receiver"></a>Vytvoření projektu s příjemce událostí funkce  
  
1.  Na řádku nabídek zvolte **soubor**, **nový**, **projektu** zobrazíte **nový projekt** dialogové okno.  
  
2.  Rozbalte **SharePoint** uzel v rámci buď **Visual C#** nebo **jazyka Visual Basic**a potom zvolte **2010** uzlu.  
  
3.  V **šablony** podokně, vyberte **projektu služby SharePoint 2010** šablony.  
  
     Tento typ projektu pro přijímačů událostí funkce použít, protože mají žádná šablona projektu.  
  
4.  V **název** zadejte **FeatureEvtTest**a potom zvolte **OK** tlačítko pro zobrazení **Průvodce vlastním nastavením SharePoint**.  
  
5.  Na **zadejte úroveň lokality a zabezpečení pro ladění** stránky, zadejte adresu URL pro web služby SharePoint server, do které chcete přidat novou položku vlastní pole nebo použijte výchozí umístění (http://\<*systému název*> /).  
  
6.  V **co je úrovně důvěryhodnosti pro toto řešení služby SharePoint?** zvolte **nasadit jako řešení farmy** tlačítko.  
  
     Další informace o řešení v izolovaném prostoru a řešení ve farmách najdete v tématu [v izolovaném prostoru aspekty řešení](../sharepoint/sandboxed-solution-considerations.md).  
  
7.  Vyberte **Dokončit** tlačítko a pak Všimněte si, že funkce, která je s názvem Feature1 se zobrazí pod **funkce** uzlu.  
  
## <a name="adding-an-event-receiver-to-the-feature"></a>Přidávání do funkci přijímače událostí  
 V dalším kroku přidejte příjemce událostí s funkcí a přidejte kód, který provede, když se tato funkce je deaktivována.  
  
#### <a name="to-add-an-event-receiver-to-the-feature"></a>Chcete-li přidat funkci přijímače událostí  
  
1.  Otevřete místní nabídku pro uzel funkce a potom zvolte **přidat funkce** vytvořit funkci.  
  
2.  V části **funkce** uzlu, otevřete místní nabídku pro **Feature1**a potom zvolte **přidat příjemce událostí** přidat příjemce událostí s funkcí.  
  
     Tento postup přidá soubor kódu v rámci Feature1. V takovém případě je název Feature1.EventReceiver.cs nebo Feature1.EventReceiver.vb, v závislosti na jazyk vývoj vašeho projektu.  
  
3.  Pokud váš projekt je napsána v [!INCLUDE[csprcs](../sharepoint/includes/csprcs-md.md)], přidejte následující kód v horní části příjemce událostí, pokud ještě není:  
  
     [!code-csharp[SP_FeatureEvt#1](../sharepoint/codesnippet/CSharp/featureevttest2/features/feature1/feature1.eventreceiver.cs#1)]  
  
4.  Třída příjemce událostí obsahuje několik metod komentované, které fungují jako události. Nahraďte **FeatureDeactivating** metoda následujícím kódem:  
  
     [!code-vb[SP_FeatureEvt#2](../sharepoint/codesnippet/VisualBasic/featureevt2vb/features/feature1/feature1.eventreceiver.vb#2)]
     [!code-csharp[SP_FeatureEvt#2](../sharepoint/codesnippet/CSharp/featureevttest2/features/feature1/feature1.eventreceiver.cs#2)]  
  
## <a name="testing-the-feature-event-receiver"></a>Testování příjemce událostí funkce  
 V dalším kroku deaktivovat funkci tak, aby test jestli **FeatureDeactivating** metoda výstupy oznámení do seznamu SharePoint oznámení.  
  
#### <a name="to-test-the-feature-event-receiver"></a>K testování příjemce událostí funkce  
  
1.  Nastavte hodnotu projektu **konfigurace nasazení služby Active** vlastnost **bez aktivace**.  
  
     Nastavení této vlastnosti brání funkci Aktivace ve službě SharePoint a umožňuje ladění přijímačů událostí funkce. Další informace najdete v tématu [ladění řešení služby SharePoint](../sharepoint/debugging-sharepoint-solutions.md).  
  
2.  Vyberte **F5** klíč, který chcete spustit projekt a nasaďte ho do služby SharePoint.  
  
3.  V horní části stránky webu SharePoint, otevřete **Akce webu** nabídce a potom zvolte **nastavení lokality**.  
  
4.  V části **Akce webu** části **nastavení lokality** vyberte **spravovat funkce webu** odkaz.  
  
5.  Na **funkce** vyberte **aktivovat** vedle položky **FeatureEvtTest Feature1** funkce.  
  
6.  Na **funkce** vyberte **deaktivovat** vedle položky **FeatureEvtTest Feature1** funkce a potom vyberte **deaktivovat tuto funkci**  potvrzení odkaz deaktivovat funkci.  
  
7.  Vyberte **Domů** tlačítko.  
  
     Všimněte si, že se zobrazí oznámení v **oznámení** seznamu po deaktivaci funkci.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytvoření přijímače událostí](../sharepoint/how-to-create-an-event-receiver.md)   
 [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)  
  
  