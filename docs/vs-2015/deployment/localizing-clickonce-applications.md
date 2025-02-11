---
title: Lokalizace aplikací ClickOnce | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
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
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 3c29bd6a58d510d98f2a08c96d0cd0bc774e197e
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65680004"
---
# <a name="localizing-clickonce-applications"></a>Lokalizace aplikací ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Lokalizace je proces zpřístupnění aplikace vhodné pro konkrétní jazykovou verzi. Tento proces zahrnuje text uživatelského rozhraní (UI) pro jazyk specifický pro oblast, pomocí správné datum a formátování měny, nastavení velikosti ovládacích prvků ve formuláři, překlad a zrcadlení ovládací prvky zprava doleva v případě potřeby.  
  
 Lokalizace aplikace výsledky při vytváření satelitních sestavení pro jeden nebo více. Každé sestavení obsahuje řetězce, obrázky a další prostředky, které jsou specifické pro danou jazykovou verzi uživatelského rozhraní. (Hlavní spustitelný soubor aplikace obsahuje řetězce pro výchozí jazykovou verzi pro vaši aplikaci.)  
  
 Toto téma popisuje tři způsoby, jak nasadit [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikací pro jiné jazykové verze:  
  
- Zahrňte všechny satelitní sestavení v jednom nasazení.  
  
- Generovat jedno nasazení pro jednotlivé jazykové verze, s jediným satelitním sestavením v každém.  
  
- Stáhněte si satelitních sestavení na vyžádání.  
  
## <a name="including-all-satellite-assemblies-in-a-deployment"></a>V nasazení včetně všech satelitních sestavení  
 Místo publikování více [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] nasazení, můžete publikovat jediné [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] nasazení, které obsahuje všechny satelitní sestavení.  
  
 Tato metoda je výchozím nastavení v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. Chcete-li použít tuto metodu v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], nemusíte dělat nic dalšího.  
  
 Při použití této metody s MageUI.exe, musíte nastavit jazykovou verzi pro vaši aplikaci do **neutrální** v MageUI.exe. Dále musíte ručně zahrnout všechny satelitní sestavení ve vašem nasazení. V MageUI.exe, můžete přidat pomocí satelitních sestavení **naplnit** tlačítko **soubory** karta manifestu aplikace.  
  
 Výhodou tohoto přístupu je, že vytváří jedno nasazení a zjednodušuje váš příběh lokalizované nasazení. V době běhu příslušného satelitního sestavení se použije, v závislosti na výchozí jazykovou verzi operačního systému uživatele Windows. Nevýhod tohoto přístupu je, že stáhne všechny satelitní sestavení pokaždé, když se aplikace instalaci nebo aktualizaci na klientském počítači. Pokud vaše aplikace má velký počet řetězců nebo vaši zákazníci mají pomalé síťové připojení, tento proces může ovlivnit výkon při aktualizaci aplikace.  
  
> [!NOTE]
> Tento přístup předpokládá, že aplikace nastaví výšku, šířku a umístění ovládacích prvků automaticky tak, aby vyhovovaly velikosti řetězce jiným textovým v různé jazykové verze. Windows Forms obsahuje celou řadu ovládacích prvků a technologie, které vám umožní navrhnout vaše formuláře tak, aby ji snadno lokalizovatelný, včetně <xref:System.Windows.Forms.FlowLayoutPanel> a <xref:System.Windows.Forms.TableLayoutPanel> ovládací prvky také <xref:System.Windows.Forms.Control.AutoSize%2A> vlastnost.  Viz také [jak: Podpora lokalizace ve formulářích Windows pomocí AutoSize a TableLayoutPanel – ovládací prvek](https://msdn.microsoft.com/library/1zkt8b33\(v=vs.110\)).  
  
## <a name="generate-one-deployment-for-each-culture"></a>Generovat jedno nasazení pro každou jazykovou verzi  
 V této strategii nasazení můžete generovat více nasazení. Každé nasazení zahrnout pouze do satelitního sestavení potřebné pro konkrétní jazykovou verzi a označit nasazení jako specifické pro danou jazykovou verzi.  
  
 Chcete-li použít tuto metodu v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], nastavte **jazyk publikování** vlastnost **publikovat** kartu na požadovanou oblast. [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] automaticky zahrne požadované pro tuto oblast a vyloučí všechny ostatní satelitní sestavení nasazení satelitního sestavení.  
  
 Totéž lze provést pomocí nástroje MageUI.exe v Microsoftu [!INCLUDE[winsdklong](../includes/winsdklong-md.md)]. Použití **naplnit** tlačítko **soubory** karta manifestu aplikace vyloučit všechny ostatní satelitní sestavení z adresáře aplikace, a pak **jazykovou verzi**pole na **název** karta manifestu nasazení v MageUI.exe. Tyto kroky zahrnují nejen správné satelitní sestavení, ale také nastavit `language` atribut na `assemblyIdentity` elementu v manifestu nasazení na odpovídající jazykovou verzi.  
  
 Po publikování aplikace, musí tento krok opakujte pro každý další jazykové verze vaše aplikace podporuje. Ujistěte se, že publikujete do jiného adresáře webového serveru nebo adresář sdílené složky souboru pokaždé, protože každý manifest aplikace bude odkazovat na různé satelitní sestavení, a každý manifest nasazení bude mít jinou hodnotu pro `language`atribut.  
  
## <a name="downloading-satellite-assemblies-on-demand"></a>Stahování satelitních sestavení na vyžádání  
 Pokud se rozhodnete zahrnout všechny satelitní sestavení v jednom nasazení, můžete zlepšit výkon pomocí stažení na vyžádání, což vám umožní označit sestavení jako volitelné. Označená sestavení nebude stažen při instalaci nebo aktualizaci aplikace. Můžete nainstalovat sestavení, když je budete potřebovat voláním <xref:System.Deployment.Application.ApplicationDeployment.DownloadFileGroup%2A> metodu <xref:System.Deployment.Application.ApplicationDeployment> třídy.  
  
 Stahování satelitních sestavení na vyžádání se mírně liší ve stahování dalších typů sestavení na vyžádání. Pro další informace a praktické příklady o tom, jak povolit tento scénář používání [!INCLUDE[winsdkshort](../includes/winsdkshort-md.md)] nástroje pro sadu [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)], naleznete v tématu [názorný postup: Stahování satelitních sestavení na vyžádání pomocí rozhraní API nasazení ClickOnce](../deployment/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api.md).  
  
 Můžete také povolit tento scénář v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  Viz také [názorný postup: Stahování satelitních sestavení na vyžádání pomocí nasazení ClickOnce pomocí návrháře rozhraní API](https://msdn.microsoft.com/library/ms366788\(v=vs.110\)) nebo [názorný postup: Stahování satelitních sestavení na vyžádání pomocí nasazení ClickOnce pomocí návrháře rozhraní API](https://msdn.microsoft.com/library/ms366788\(v=vs.120\)).  
  
## <a name="testing-localized-clickonce-applications-before-deployment"></a>Testování lokalizovaných aplikací ClickOnce před nasazením  
 Satelitní sestavení se použije pro Windows Forms pouze pokud aplikaci <xref:System.Threading.Thread.CurrentUICulture%2A> pro hlavního vlákna aplikace je nastavena na jazykovou verzi satelitního sestavení. Zákazníci místního trzích, kde bude pravděpodobně už běží lokalizovanou verzi sady Windows s jejich jazyková verze nastavena na vhodné výchozí nastavení.  
  
 Existují tři možnosti pro testování předtím, než je vaše aplikace je možné zákazníkům zpřístupnit lokalizovaných nasazení:  
  
- Můžete spustit váš [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikace na příslušný lokalizovaných verzích Windows.  
  
- Můžete nastavit <xref:System.Threading.Thread.CurrentUICulture%2A> vlastnost prostřednictvím kódu programu ve vaší aplikaci. (Tato vlastnost musí být nastavena dříve než zavoláte <xref:System.Windows.Forms.Application.Run%2A> metoda.)  
  
## <a name="see-also"></a>Viz také  
 [\<Vlastnost assemblyIdentity > – Element](../deployment/assemblyidentity-element-clickonce-deployment.md)   
 [ClickOnce – zabezpečení a nasazení](../deployment/clickonce-security-and-deployment.md)   
 [Globalizace modelu Windows Forms](https://msdn.microsoft.com/library/72f6cd92-83be-45ec-aa37-9cb8e3ebc3c5)
