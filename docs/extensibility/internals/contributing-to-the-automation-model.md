---
title: "Přispívání do modelu automatizace | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: automation [Visual Studio SDK]
ms.assetid: 44de482d-93c8-41a4-843c-cefda995a03e
caps.latest.revision: "18"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5907f540e5f81e26b7d184352e3c38531ec5da66
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="contributing-to-the-automation-model"></a>Přispívání do modelu automatizace
Visual Studio poskytuje sadu rozhraní automatizace pro přizpůsobení prostředí. Model automatizace je objektový model, který umožňuje koncovým uživatelům vytvářet doplňky sady Visual Studio a rozšíření.  
  
 Kromě toho je vhodné pro vás, jako vývojář VSPackage přispívat k automatizaci modelu; Tímto způsobem můžete povolit koncovým uživatelům vaší VSPackage vytvořit doplňky a obecně zajistit konzistentní prostředí modelu při použití vašeho VSPackage v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 Chcete-li konzistentní prostředí koncového uživatele, můžete podle sadu pokyny při navrhování vaší VSPackage tak, aby model automatizace pro vaše VSPackage následuje nápady v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Přehled modelu automatizace](../../extensibility/internals/automation-model-overview.md)  
 Definuje automation model jako související skupiny objektů, které řídí hlavní omezující vlastnosti pro běžné prostředí. Tuto sadu objektů je obrázku v diagramu modelu automatizace.  
  
 [Poskytnutí automatizace pro VSPackages](../../extensibility/internals/providing-automation-for-vspackages.md)  
 Popisuje, k dispozici automatizace pro vaše VSPackage dvě hlavní možnosti.  
  
 [Vystavení objektů projektu](../../extensibility/internals/exposing-project-objects.md)  
 Poskytuje podrobné pokyny pro vytvoření VSPackage konkrétní objekty.  
  
 [Projekt modelování](../../extensibility/internals/project-modeling.md)  
 Popisuje standardní projektu objekty, které jsou potřebné k automatizaci nového typu projektu a ukazuje cestu, která odpovídá automatizace projektu. Toto téma obsahuje také výpisech deklarací a implementaci pro třídy.  
  
 [Vystavení události](../../extensibility/internals/exposing-events-in-the-visual-studio-sdk.md)  
 Poskytuje podrobné pokyny pro vytvoření události pro váš model automatizace.  
  
 [Podpora automatizace pro možnosti stránky](../../extensibility/internals/automation-support-for-options-pages.md)  
 Popisuje, jak vrátit objekt automatizace pro podporu vlastnosti VSPackage vlastní **možnosti** dialogové okno na **nástroj** nabídky tím, že rozšíří `DTE.Properties` objektu.  
  
 [Poskytnutí automatizace pro kód](../../extensibility/internals/providing-automation-for-code.md)  
 Vysvětluje, že vytvoření automatizace modelu kódu se nevyžaduje. Odkaz je však zadat v tomto tématu, která poskytuje pronikavého informace do kód – modely.  
  
 [Postupy: poskytování automatizace pro Windows](../../extensibility/internals/how-to-provide-automation-for-windows.md)  
 Vysvětluje, že poskytuje automatizace je vhodné vždy, když chcete zpřístupnit objekty automatizace v okně prostředí a prostředí již neposkytuje objekt připravených automatizace. Popisuje automatizace pro nástroje systému windows a windows dokumentu.  
  
 [Pomocí modelu automatizace](../../extensibility/internals/using-the-automation-model.md)  
 Obsahuje dva příklady kódu, které ukazují, jak příjemce automatizace získá počáteční projekt objekty automatizace.  
  
 [Pro konfiguraci a SelectedItem objekty automatizace](../../extensibility/internals/automation-for-configuration-and-selecteditem-objects.md)  
 Poskytuje informace o automatizaci pro možnosti konfigurace a automatizace pro vybrané položky.  
  
## <a name="reference"></a>Odkaz  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A>  
 Poskytuje ukázka kódu, který ukazuje, jak VSPackage účastní DTE automatizace objektový model. Uvádí parametry a návratové hodnoty, vybrané poznámky.  
  
## <a name="related-sections"></a>Související oddíly