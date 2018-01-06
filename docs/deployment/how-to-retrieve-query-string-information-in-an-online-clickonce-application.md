---
title: "Postupy: načtení informací řetězce dotazu do Online aplikace ClickOnce | Microsoft Docs"
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
- ClickOnce deployment, query strings
- query strings, retrieving information
ms.assetid: 48ce098a-a075-481b-a5f5-c8ba11f63120
caps.latest.revision: "19"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: e0fb359dba89a3eef6f257b0cfe560a3f3ab5738
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-retrieve-query-string-information-in-an-online-clickonce-application"></a>Postupy: Načtení informací řetězce dotazu do online aplikace ClickOnce
*Řetězec dotazu* je část adresy URL začínající otazník (?), který obsahuje libovolné informace ve formě *název = hodnota*. Předpokládejme, že máte [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikaci s názvem `WindowsApp1` který je hostitelem na `servername`, a vy chcete předat hodnotu pro proměnnou `username` při spuštění aplikace. Adresa URL může vypadat následovně:  
  
 `http://servername/WindowsApp1.application?username=joeuser`  
  
 Následující dva postupy ukazují, jak používat [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace za účelem získání informací řetězce dotazu.  
  
> [!NOTE]
>  Pokud je vaše aplikace spuštěna pomocí protokolu HTTP, místo použití sdílené složky nebo místního systému souborů, můžete předat pouze informace v řetězci dotazu.  
  
 První postup znázorňuje způsob vaší [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace můžete použít malou část kódu ke čtení tyto hodnoty při spuštění aplikace.  
  
 Následující postup ukazuje, jak nakonfigurovat vaše [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace pomocí MageUI.exe tak, aby přijímal parametrů řetězce dotazu. Musíte se k tomu vždy, když publikujete aplikaci.  
  
> [!NOTE]
>  Před rozhodnutím o povolení této funkce, najdete v části "Zabezpečení" dál v tomto tématu.  
  
 Informace o tom, jak vytvořit [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] najdete v části nasazení pomocí Mage.exe nebo MageUI.exe, [návod: Ruční nasazení aplikace ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md).  
  
> [!NOTE]
>  Od verze rozhraní .NET Framework 3.5 SP1, je možné předat argumenty příkazového řádku offline [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace. Pokud chcete zadat argumenty pro aplikace, můžete předat parametry do souboru zástupce s. Rozšíření APPREF MS.  
  
### <a name="to-obtain-query-string-information-from-a-clickonce-application"></a>K získání informací řetězce dotazu z aplikace ClickOnce  
  
1.  Vložte následující kód ve vašem projektu. Aby pro tento kód funkce, je nutné mít odkaz na System.Web a přidejte `using` nebo `Imports` příkazy pro System.Web, System.Collections.Specialized a System.Deployment.Application.  
  
     [!code-csharp[ClickOnceQueryString#1](../deployment/codesnippet/CSharp/how-to-retrieve-query-string-information-in-an-online-clickonce-application_1.cs)]
     [!code-vb[ClickOnceQueryString#1](../deployment/codesnippet/VisualBasic/how-to-retrieve-query-string-information-in-an-online-clickonce-application_1.vb)]  
  
2.  Volání funkce definované dříve k načtení <xref:System.Collections.DictionaryBase.Dictionary%2A> parametrů řetězce dotazu, indexované podle názvu.  
  
### <a name="to-enable-query-string-passing-in-a-clickonce-application-with-mageuiexe"></a>Chcete-li povolit řetězec dotazu předávání v aplikaci ClickOnce s MageUI.exe  
  
1.  Otevřete příkazový řádek .NET a zadejte:  
  
    ```  
    MageUI  
    ```  
  
2.  Z **soubor** nabídce vyberte možnost **otevřete**a otevřete manifest nasazení pro vaše [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikaci, které je soubor končící na `.application` rozšíření.  
  
3.  Vyberte **možnosti nasazení** panelu v levém navigačním okně a vyberte **parametry povolit adresu URL pro aplikaci** zaškrtávací políčko.  
  
4.  Z **soubor** nabídce vyberte možnost **Uložit**.  
  
> [!NOTE]
>  Alternativně můžete povolit řetězec dotazu předávání v [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]. Vyberte **parametry povolit adresu URL pro aplikaci** zaškrtávací políčko, které lze nalézt tak, že otevřete **vlastnosti projektu**, vyberete **publikovat** kartě, kliknutím na **Možnosti** tlačítko a pak vybrat **manifesty**.  
  
## <a name="robust-programming"></a>Robustní programování  
 Při použití parametrů řetězce dotazu, musí dát pečlivě zvážit na tom, jak je aplikace nainstalovaná a aktivovaná. Pokud vaše aplikace je nastavena k instalaci na počítač uživatele z webu nebo v síťové sdílené složce, je pravděpodobné, že uživatel aktivuje aplikaci pouze jednou prostřednictvím adresy URL. Potom uživatel obvykle aktivuje aplikaci pomocí zástupce v **spustit** nabídky. V důsledku toho aplikace záruku, že se na argumenty řetězce dotazu pouze jednou během celé jeho životnosti. Pokud se rozhodnete ukládat tyto argumenty na počítači uživatele pro budoucí použití, jste zodpovědní za uložení je v bezpečném režimu.  
  
 Pokud vaše aplikace je online pouze, je vždy aktivovat prostřednictvím adresy URL. I v takovém případě však aplikace musí být zapsané do fungovat správně, pokud jsou parametrů řetězce dotazu chybí nebo je poškozený.  
  
## <a name="net-framework-security"></a>Zabezpečení rozhraní .NET Framework  
 Povolit předávání parametrů URL vaší [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace jenom v případě, že máte v úmyslu čistit vstup od všech škodlivých znaků před jeho použitím. Řetězec vložených uvozovky, lomítka nebo středníky, například, může provádět libovolná data operace pokud používá nefiltrovaná v dotazu SQL databázi. Další informace o zabezpečení řetězců dotazů najdete v tématu [Přehled zneužití skriptu](http://msdn.microsoft.com/Library/772c7312-211a-4eb3-8d6e-eec0aa1dcc07).  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečování aplikací ClickOnce](../deployment/securing-clickonce-applications.md)