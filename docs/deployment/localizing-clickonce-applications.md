---
title: Lokalizace aplikací ClickOnce | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- WPF, ClickOnce applications
- ClickOnce deployment, globalization
- deploying applications [ClickOnce], localizing ClickOnce applications
- localization, ClickOnce deployment
- ClickOnce deployment, download on-demand
- ClickOnce deployment, localization
- Windows Forms, ClickOnce applications
- console applications, ClickOnce applications
ms.assetid: c92b193b-054d-4923-834b-d4226a4c7a1a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c3d7ebc762c7b1feb895323f7ef9ee0180ce954e
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="localizing-clickonce-applications"></a>Lokalizace aplikací ClickOnce
Lokalizace je proces vytváření aplikace vhodné pro konkrétní jazykové verze. Tento proces zahrnuje překlad text v uživatelském rozhraní (UI) na oblast konkrétní jazyk pomocí správné datum a formátování měny, nastavení velikosti ovládacích prvků ve formuláři, a zrcadlení ovládacích prvků zprava doleva v případě potřeby.  
  
 Lokalizace aplikací výsledky při vytváření satelitních sestavení jeden nebo více. Každé sestavení obsahuje řetězce, Image a další prostředky, které jsou specifické pro danou jazykové verze uživatelského rozhraní. (Hlavní spustitelný soubor aplikace obsahuje řetězce pro výchozí jazykovou verzi pro vaši aplikaci.)  
  
 Toto téma popisuje tři způsoby, jak nasadit [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace pro jiné jazykové verze:  
  
-   Zahrňte všechny satelitní sestavení v jednom nasazení.  
  
-   Generovat jedno nasazení pro každou jazykovou verzi s jedno satelitní sestavení jednotlivých součástí.  
  
-   Stahování satelitních sestavení na vyžádání.  
  
## <a name="including-all-satellite-assemblies-in-a-deployment"></a>V nasazení, včetně všech satelitních sestavení  
 Místo publikování více [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení, můžete publikovat v jedné [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení, které obsahuje všechny satelitní sestavení.  
  
 Tato metoda je výchozím nastavení v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Chcete-li použít tuto metodu v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], nemusíte dělat nic dalšího.  
  
 Chcete-li použít tuto metodu s MageUI.exe, musíte nastavit jazykovou verzi pro vaše aplikace a **neutrální** v MageUI.exe. Dále musíte ručně zahrnout všechny satelitní sestavení ve vašem nasazení. V MageUI.exe, můžete přidat satelitní sestavení pomocí **vyplnit** tlačítko **soubory** kartě manifest aplikace.  
  
 Výhodou tohoto přístupu je, že vytvoří jediné nasazení a zjednodušuje příběhu lokalizované nasazení. V době běhu odpovídající satelitní sestavení se použije, v závislosti na výchozí jazykovou verzi operačního systému Windows uživatele. Z nevýhod tohoto přístupu je, že stáhne všechny satelitní sestavení vždy, když aplikace je instalace nebo aktualizace na klientském počítači. Pokud vaše aplikace má velký počet řetězce nebo vašim zákazníkům mají pomalé síťové připojení, tento proces může ovlivnit výkon při aktualizaci aplikace.  
  
> [!NOTE]
>  Tento přístup předpokládá, že aplikace nastaví výšku, šířku a umístění ovládacích prvků automaticky, aby dokázala pojmout velikost řetězce jiným textovým v různých jazykových verzích. Windows Forms obsahuje celou řadu ovládacích prvků a technologie, které vám umožní navrhnout formulář tak, aby byl snadno lokalizovatelný, včetně <xref:System.Windows.Forms.FlowLayoutPanel> a <xref:System.Windows.Forms.TableLayoutPanel> ovládací prvky a taky <xref:System.Windows.Forms.Control.AutoSize%2A> vlastnost.  Viz také [postupy: lokalizace podpora v systému Windows Forms pomocí AutoSize a TableLayoutPanel – ovládací prvek](http://msdn.microsoft.com/library/1zkt8b33\(v=vs.110\)).  
  
## <a name="generate-one-deployment-for-each-culture"></a>Generovat jedno nasazení pro každou jazykovou verzi  
 V této strategie nasazení můžete generovat více nasazení. V každé nasazení zahrnete pouze satelitní sestavení pro konkrétní jazykové verze potřeba a označit nasazení jako specifické pro danou jazykovou verzi.  
  
 Chcete použít tuto metodu v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], nastavte **jazyk publikování** vlastnost **publikovat** kartě na požadovanou oblast. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] automaticky zahrne satelitní sestavení požadované pro oblast vyberete a vyloučí všechny ostatní satelitních sestavení z nasazení.  
  
 Totéž můžete provést pomocí nástroje MageUI.exe v Microsoft [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]. Použití **vyplnit** na tlačítko **soubory** kartě manifest aplikace chcete vyloučit jiných satelitních sestavení z adresáře aplikace a poté nastavte **jazykovou verzi**pole na **název** kartu pro manifest nasazení v MageUI.exe. Tyto kroky nejen zahrnují správné satelitní sestavení, ale také nastavit `language` atributu u `assemblyIdentity` element v manifestu nasazení na odpovídající jazykovou verzi.  
  
 Po publikování aplikace, musí tento krok opakujte pro každou další jazykovou verzi vaše aplikace podporuje. Je nutné nejprve publikovat do jiného adresáře webového serveru nebo adresář sdílené složky souboru pokaždé, když, protože každý manifest aplikace bude odkazovat na různé satelitní sestavení a každý – manifest nasazení bude mít jinou hodnotu pro `language`atribut.  
  
## <a name="downloading-satellite-assemblies-on-demand"></a>Stahování satelitních sestavení na vyžádání  
 Pokud se rozhodnete zahrnout všechny satelitní sestavení v jednom nasazení, můžete zlepšit výkon pomocí stažení na vyžádání, což umožňuje označení sestavení jako volitelné. Při instalaci nebo aktualizaci aplikace, nebudou staženy označená sestavení. Sestavení můžete instalovat, pokud budete potřebovat při volání <xref:System.Deployment.Application.ApplicationDeployment.DownloadFileGroup%2A> metodu <xref:System.Deployment.Application.ApplicationDeployment> třídy.  
  
 Stahování satelitních sestavení na vyžádání se mírně liší od stahování ostatních typů sestavení na vyžádání. Pro další informace a ukázky kódu na tom, jak povolit tento scénář pomocí [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] nástroje pro [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)], najdete v části [návod: stahování satelitních sestavení na vyžádání pomocí rozhraní API nasazení ClickOnce](../deployment/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api.md).  
  
 Můžete také povolit tento scénář v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  Viz také [návod: stahování satelitních sestavení na vyžádání pomocí ClickOnce pomocí rozhraní API nasazení návrháře](http://msdn.microsoft.com/library/ms366788\(v=vs.110\)) nebo [návod: stahování satelitních sestavení na vyžádání pomocí rozhraní API nasazení ClickOnce Pomocí návrháře](http://msdn.microsoft.com/library/ms366788\(v=vs.120\)).  
  
## <a name="testing-localized-clickonce-applications-before-deployment"></a>Testování lokalizovaných aplikací ClickOnce před nasazením  
 Satelitní sestavení se použije pro jenom Pokud aplikace Windows Forms <xref:System.Threading.Thread.CurrentUICulture%2A> pro hlavní vlákno aplikace je nastavena na jazykovou verzi satelitní sestavení. Zákazníci na místních trzích budou pravděpodobně používat lokalizované verzi systému Windows s jejich jazykovou verzi nastavenou na odpovídající výchozí.  
  
 Máte tři možnosti pro testování lokalizovaných nasazení před zpřístupněním aplikace k dispozici zákazníkům:  
  
-   Můžete spustit vaší [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikací na odpovídající lokalizované verze systému Windows.  
  
-   Můžete nastavit <xref:System.Threading.Thread.CurrentUICulture%2A> vlastnost prostřednictvím kódu programu ve vaší aplikaci. (Tato vlastnost musí být nastavena, před voláním <xref:System.Windows.Forms.Application.Run%2A> metoda.)  
  
## <a name="see-also"></a>Viz také  
 [\<assemblyIdentity > elementu](../deployment/assemblyidentity-element-clickonce-deployment.md)   
 [ClickOnce – zabezpečení a nasazení](../deployment/clickonce-security-and-deployment.md)   
 [Globalizace modelu Windows Forms](/dotnet/framework/winforms/advanced/globalizing-windows-forms)