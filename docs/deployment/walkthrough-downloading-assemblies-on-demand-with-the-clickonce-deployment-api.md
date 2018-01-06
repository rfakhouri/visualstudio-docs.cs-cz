---
title: "Návod: Stahování sestavení na vyžádání pomocí rozhraní API nasazení ClickOnce | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- assemblies, downloading [ClickOnce]
- ClickOnce deployment, on-demand download
- on-demand assemblies, ClickOnce
ms.assetid: d20e2789-8621-4806-b5b7-841122da1456
caps.latest.revision: "16"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 640c0852a3745d11aae119e3c00e024b594d9132
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api"></a>Návod: Stahování sestavení na vyžádání pomocí rozhraní API nasazení ClickOnce
Ve výchozím nastavení, všechna sestavení součástí [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace se stáhnou při prvním spuštění aplikace. Ale může mít části aplikace, které jsou používány malého uživatelů. V takovém případě budete chtít stáhnout sestavení, pouze když vytváříte jeden z jeho typů. Následující postup ukazuje, jak označit určité sestavení v aplikaci jako "volitelné", a jak je stáhnout pomocí tříd v <xref:System.Deployment.Application> obor názvů při common language runtime (CLR) požaduje.  
  
> [!NOTE]
>  Vaše aplikace bude nutné spustit v úplný vztah důvěryhodnosti pomocí tohoto postupu.  
  
## <a name="prerequisites"></a>Požadavky  
 Budete potřebovat jeden z následujících součástí pro dokončení tohoto návodu:  
  
-   Sady Windows SDK. Sada Windows SDK můžete stáhnout z webu Microsoft Download Center.  
  
-   Visual Studio.  
  
## <a name="creating-the-projects"></a>Vytváření projektů  
  
#### <a name="to-create-a-project-that-uses-an-on-demand-assembly"></a>Chcete-li vytvořit projekt, který používá sestavení na vyžádání  
  
1.  Vytvořte adresář s názvem ClickOnceOnDemand.  
  
2.  Otevřete příkazový řádek Windows SDK nebo [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] příkazového řádku.  
  
3.  Přejděte do adresáře ClickOnceOnDemand.  
  
4.  Vygenerujte pár veřejného a privátního klíče pomocí následujícího příkazu:  
  
    ```  
    sn -k TestKey.snk  
    ```  
  
5.  Pomocí programu Poznámkový blok nebo jiném textovém editoru, definovat třídu s názvem `DynamicClass` s jedinou vlastností s názvem `Message`.  
  
     [!code-vb[ClickOnceLibrary#1](../deployment/codesnippet/VisualBasic/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api_1.vb)]
     [!code-csharp[ClickOnceLibrary#1](../deployment/codesnippet/CSharp/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api_1.cs)]  
  
6.  Uložte text jako soubor s názvem `ClickOnceLibrary.cs` nebo `ClickOnceLibrary.vb`, v závislosti na jazyk, který používáte, k adresáři ClickOnceOnDemand.  
  
7.  Zkompilujte soubor do sestavení.  
  
    ```csharp  
    csc /target:library /keyfile:TestKey.snk ClickOnceLibrary.cs  
    ```  
  
    ```vb  
    vbc /target:library /keyfile:TestKey.snk ClickOnceLibrary.vb  
    ```  
  
8.  Chcete-li získat token veřejného klíče pro sestavení, použijte následující příkaz:  
  
    ```  
    sn -T ClickOnceLibrary.dll  
    ```  
  
9. Vytvořte nový soubor pomocí textového editoru a zadejte následující kód. Tento kód vytvoří aplikace Windows Forms, který stáhne sestavení ClickOnceLibrary, pokud je to požadováno.  
  
     [!code-csharp[ClickOnceOnDemandCmdLine#1](../deployment/codesnippet/CSharp/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api_2.cs)]
     [!code-vb[ClickOnceOnDemandCmdLine#1](../deployment/codesnippet/VisualBasic/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api_2.vb)]  
  
10. V kódu, vyhledejte volání <xref:System.Reflection.Assembly.LoadFile%2A>.  
  
11. Nastavit`PublicKeyToken` na hodnotu, která jste získali dříve.  
  
12. Uložte soubor jako `Form1.cs` nebo `Form1.vb`.  
  
13. Zkompilujte do spustitelný soubor pomocí následujícího příkazu.  
  
    ```csharp  
    csc /target:exe /reference:ClickOnceLibrary.dll Form1.cs  
    ```  
  
    ```vb  
    vbc /target:exe /reference:ClickOnceLibrary.dll Form1.vb  
    ```  
  
## <a name="marking-assemblies-as-optional"></a>Označení sestavení jako volitelný  
  
#### <a name="to-mark-assemblies-as-optional-in-your-clickonce-application-by-using-mageuiexe"></a>K označení sestavení jako volitelný v aplikaci ClickOnce pomocí MageUI.exe  
  
1.  Vytvořte manifest aplikace pomocí MageUI.exe, jak je popsáno v [návod: Ruční nasazení aplikace ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md). Pro manifest aplikace použijte následující nastavení:  
  
    -   Název manifestu aplikace `ClickOnceOnDemand`.  
  
    -   Na **soubory** stránce v řádku ClickOnceLibrary.dll nastavte **typ souboru** sloupec, který se **žádné**.  
  
    -   Na **soubory** stránky v řádku ClickOnceLibrary.dll typ `ClickOnceLibrary.dll` v **skupiny** sloupce.  
  
2.  Pomocí MageUI.exe vytvoření manifestu nasazení, jak je popsáno v [návod: Ruční nasazení aplikace ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md). Pro manifest nasazení použijte následující nastavení:  
  
    -   Název manifestu nasazení `ClickOnceOnDemand`.  
  
## <a name="testing-the-new-assembly"></a>Testování nového sestavení  
  
#### <a name="to-test-your-on-demand-assembly"></a>K testování vaší sestavení na vyžádání  
  
1.  Nahrát váš [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení na webový server.  
  
2.  Spusťte aplikaci nasazenou s [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] z webového prohlížeče zadáním adresy URL manifestu nasazení. Když zavoláte vaše [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace `ClickOnceOnDemand`a nahrajte ho do kořenového adresáře adatum.com, adresa URL bude vypadat takto:  
  
    ```  
    http://www.adatum.com/ClickOnceOnDemand/ClickOnceOnDemand.application  
    ```  
  
3.  Jakmile se zobrazí hlavní formulář, stiskněte <xref:System.Windows.Forms.Button>. Měli byste vidět řetězec v okně zprávy, který čte "Hello, World!".  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Deployment.Application.ApplicationDeployment>