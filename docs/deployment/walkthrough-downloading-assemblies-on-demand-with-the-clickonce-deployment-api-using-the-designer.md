---
title: 'Návod: Stahování sestavení na vyžádání pomocí nasazení ClickOnce pomocí návrháře rozhraní API | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- assemblies, downloading [ClickOnce]
- Windows applications, ClickOnce deployments
- ClickOnce deployment, on-demand download
- on-demand assemblies, ClickOnce
ms.assetid: 59a0dd5f-1cab-4f2f-b780-0ab7399905d5
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 247487277052cf488907ba97393519b1fca44f3d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer"></a>Návod: Stahování sestavení na vyžádání pomocí rozhraní API nasazení ClickOnce pomocí Návrháře
Ve výchozím nastavení, všechna sestavení součástí [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace se stáhnou při prvním spuštění aplikace. Však může být částí aplikace, které jsou používány malého uživatelů. V takovém případě budete chtít stáhnout sestavení, pouze když vytváříte jeden z jeho typů. Následující postup ukazuje, jak označit určité sestavení v aplikaci jako "volitelné", a jak je stáhnout pomocí tříd v <xref:System.Deployment.Application> obor názvů, když je modul common language runtime požaduje.  
  
> [!NOTE]
>  Vaše aplikace bude nutné spustit v úplný vztah důvěryhodnosti pomocí tohoto postupu.  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, klikněte na tlačítko **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="creating-the-projects"></a>Vytváření projektů  
  
#### <a name="to-create-a-project-that-uses-an-on-demand-assembly-with-visual-studio"></a>Chcete-li vytvořit projekt, který používá sestavení na vyžádání pomocí sady Visual Studio  
  
1.  Vytvoření nového projektu Windows Forms v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Na **soubor** nabídky, přejděte na příkaz **přidat**a potom klikněte na **nový projekt**. Vyberte **knihovny tříd** projektu v dialogovém okně a pojmenujte ji `ClickOnceLibrary`.  
  
    > [!NOTE]
    >  V jazyce Visual Basic, doporučujeme úpravě vlastností projektu změnit kořenového oboru názvů pro tento projekt na `Microsoft.Samples.ClickOnceOnDemand` nebo do oboru názvů podle svého výběru. Pro jednoduchost dva projekty v tomto průvodci jsou ve stejném oboru názvů.  
  
2.  Definice třídy s názvem `DynamicClass` s jedinou vlastností s názvem `Message`.  
  
     [!code-vb[ClickOnceLibrary#1](../deployment/codesnippet/VisualBasic/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer_1.vb)]
     [!code-csharp[ClickOnceLibrary#1](../deployment/codesnippet/CSharp/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer_1.cs)]  
  
3.  Vyberte projekt Windows Forms v **Průzkumníku řešení**. Přidat odkaz na <xref:System.Deployment.Application> sestavení a projekt odkaz na `ClickOnceLibrary` projektu.  
  
    > [!NOTE]
    >  V jazyce Visual Basic, doporučujeme úpravě vlastností projektu změnit kořenového oboru názvů pro tento projekt na `Microsoft.Samples.ClickOnceOnDemand` nebo do oboru názvů podle svého výběru. Pro jednoduchost dva projekty v tomto návodu nacházejí ve stejném oboru názvů.  
  
4.  Klikněte pravým tlačítkem na formulář, klikněte na tlačítko **kód zobrazení** v nabídce a přidejte následující odkazy na formuláři.  
  
     [!code-csharp[ClickOnceOnDemand#1](../deployment/codesnippet/CSharp/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer_2.cs)]
     [!code-vb[ClickOnceOnDemand#1](../deployment/codesnippet/VisualBasic/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer_2.vb)]  
  
5.  Přidejte následující kód ke stažení toto sestavení na vyžádání. Tento kód ukazuje, jak k mapování sadu sestavení na název skupiny pomocí Obecné <xref:System.Collections.DictionaryBase.Dictionary%2A> třídy. Protože stahujete pouze jednoho sestavení v tomto průvodci, je pouze jeden sestavení v naší skupiny. V reálné aplikaci byste pravděpodobně chtít stáhnout všechna sestavení spojené s jedinou funkcí v aplikaci ve stejnou dobu. Tabulky mapování umožňuje snadno to provést tím, že přidružíte všechny knihovny DLL, které patří do funkce s názvem skupiny, stahování.  
  
     [!code-csharp[ClickOnceOnDemand#2](../deployment/codesnippet/CSharp/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer_3.cs)]
     [!code-vb[ClickOnceOnDemand#2](../deployment/codesnippet/VisualBasic/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer_3.vb)]  
  
6.  Na **zobrazení** nabídky, klikněte na tlačítko **sada nástrojů**. Přetáhněte <xref:System.Windows.Forms.Button> z **sada nástrojů** do formuláře. Dvakrát klikněte na tlačítko a přidejte následující kód, který <xref:System.Windows.Forms.Control.Click> obslužné rutiny události.  
  
     [!code-csharp[ClickOnceOnDemand#3](../deployment/codesnippet/CSharp/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer_4.cs)]
     [!code-vb[ClickOnceOnDemand#3](../deployment/codesnippet/VisualBasic/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer_4.vb)]  
  
## <a name="marking-assemblies-as-optional"></a>Označení sestavení jako volitelný  
  
#### <a name="to-mark-assemblies-as-optional-in-your-clickonce-application-by-using-visual-studio"></a>Označit sestavení jako volitelný v aplikaci ClickOnce pomocí sady Visual Studio  
  
1.  Klikněte pravým tlačítkem projekt v **Průzkumníku řešení** a klikněte na tlačítko **vlastnosti**. Vyberte **publikovat** kartě.  
  
2.  Klikněte **soubory aplikace** tlačítko.  
  
3.  Vyhledejte výpis pro ClickOnceLibrary.dll. Nastavte **stav publikování** rozevíracího seznamu pro **zahrnout**.  
  
4.  Rozbalte **skupiny** rozevíracího seznamu a vyberte **nový**. Zadejte název `ClickOnceLibrary` jako název nové skupiny.  
  
5.  Pokračovat v publikování aplikace, jak je popsáno v [postupy: publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
#### <a name="to-mark-assemblies-as-optional-in-your-clickonce-application-by-using-manifest-generation-and-editing-tool--graphical-client-mageuiexe"></a>Označit sestavení jako volitelný v aplikaci ClickOnce pomocí generování manifestu a nástroj pro úpravy, grafický klient (MageUI.exe)  
  
1.  Vytvoření vaší [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifesty, jak je popsáno v [návod: Ruční nasazení aplikace ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md).  
  
2.  Před zavřením MageUI.exe, vyberte kartu, která obsahuje manifest aplikace vašeho nasazení a na této kartě vyberte **soubory** kartě.  
  
3.  Vyhledejte ClickOnceLibrary.dll v seznamu souborů aplikace a nastavit jeho **typ souboru** sloupec, který se **žádné**. Pro **skupiny** zadejte `ClickOnceLibrary.dll`.  
  
## <a name="testing-the-new-assembly"></a>Testování nového sestavení  
  
#### <a name="to-test-your-on-demand-assembly"></a>K testování vaší sestavení na vyžádání  
  
1.  Spusťte aplikaci nasazenou s [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)].  
  
2.  Jakmile se zobrazí hlavní formulář, stiskněte <xref:System.Windows.Forms.Button>. Měli byste vidět řetězec v okně zprávy, který čte "Hello, World!"  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Deployment.Application.ApplicationDeployment>