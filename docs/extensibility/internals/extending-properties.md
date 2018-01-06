---
title: "Rozšíření vlastnosti | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Properties window, providing support
ms.assetid: 68e2cbd4-861c-453f-8c9f-4ab6afc80e67
caps.latest.revision: "18"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 5c47295c1906c6517638bdf8e9c3a55897f38aa1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="extending-properties"></a>Rozšíření vlastnosti
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] **Vlastnosti** okno Prohlížeč universal vlastností pro komponenty modelu COM a modelu COM + a podporuje všechny [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] produkty. **Vlastnosti** okno pracuje s `ITypeInfo` zadejte informace a metadata modelu COM + seznam vlastnosti doby návrhu pro aktuálně vybraný objekt v jakémkoli okně integrované vývojové prostředí (IDE).  
  
 **Vlastnosti** okno, které lze otevřít stisknutím klávesy F4 nebo výběrem **vlastnosti – okno** na **zobrazení** nabídce slouží k zobrazení a úpravy Konfigurace nezávislé, návrhu vlastností a událostí vybraných objektů. Vlastnosti závislá na konfiguraci, přidružené k řešení a projekty, se zobrazí na [stránky vlastností](../../extensibility/internals/property-pages.md). Další informace najdete v tématu [vlastnosti NIB: projektu](http://msdn.microsoft.com/en-us/fb126574-24ad-4c96-9b2b-6e1f3879ba50), [Správa možnosti konfigurace](../../extensibility/internals/managing-configuration-options.md), a [správy NIB: položka v projektech](http://msdn.microsoft.com/en-us/762e606b-7f44-4b66-97a1-e30a703654a0).  
  
 ![Přehled vlastností okna](../../extensibility/internals/media/vspropertieswindow.png "vsPropertiesWindow")  
Vlastnosti – okno  
  
 Tato část obsahuje podrobné informace, které platí pro jednotlivé oblasti **vlastnosti** okno a rozhraní, které je nutné implementovat a volání k naplnění okna.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Přehled okna Vlastnosti](../../extensibility/internals/properties-window-overview.md)  
 Vysvětlující účel **vlastnosti** okno vzhledem ke okno nástroje a okna dokumentu.  
  
 [Zásady šablon a okno Vlastnosti](../../extensibility/internals/template-policy-and-the-properties-window.md)  
 Popisuje, jak je projektu obsažené v projektu šablony organizace a jak takový projekt šablony enterprise můžete vynutit zásady.  
  
 [Pole a rozhraní okna Vlastnosti](../../extensibility/internals/properties-window-fields-and-interfaces.md)  
 Vysvětluje základ pro výběr, která určuje, jaké informace se zobrazují v **vlastnosti** okno.  
  
 [Seznam objektů okna Vlastnosti](../../extensibility/internals/properties-window-object-list.md)  
 Popisuje účel **vlastnosti** okno seznam objektů, které popisují, jak, pokud jiný objekt z tohoto seznamu aktivuje volání, prostředí je informován vybral nový objekt.  
  
 [Tlačítka okna Vlastnosti](../../extensibility/internals/properties-window-buttons.md)  
 Vysvětlující účel čtyři výchozí tlačítka zobrazená na **vlastnosti** nástrojů okna.  
  
 [Zobrazení mřížky okna Vlastnosti](../../extensibility/internals/properties-display-grid.md)  
 Vysvětluje, kde názvy vlastností a pole hodnot vlastností se nacházejí v mřížce.  
  
## <a name="related-sections"></a>Související oddíly  
 [Typy projektů](../../extensibility/internals/project-types.md)  
 Popisuje projekty jako stavební kameny [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE.  
  
 [Kompilace a sestavení](../../ide/compiling-and-building-in-visual-studio.md)  
 Popisuje, jak můžete použít [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] platforma pro nepřetržitě testování a ladění aplikací, jako je vytváření.  
  
 [IDispatch](https://msdn.microsoft.com/library/windows/desktop/ms221608.aspx)  
 Popisuje `IDispatch` rozhraní, který byl původně navržený pro podporu automatizace, zajišťuje mechanizmus pozdní vazbou přístup a načíst informace o metody a vlastnosti objektu.  
  
 [Správa nastavení aplikace (.NET)](../../ide/managing-application-settings-dotnet.md)  
 Poskytuje přehled nastavení aplikace, které umožňují nakonfigurovat aplikaci tak, aby hodnoty vlastnosti jsou uloženy v externí konfigurační soubor místo zkompilovaný kód aplikace.  
  
 [Projekty a řešení](../../ide/solutions-and-projects-in-visual-studio.md)  
 Vysvětluje, jak [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] efektivně spravuje položky jako odkazy, datová připojení, složky a soubory, které jsou vyžadované úsilí vývoje prostřednictvím řešení a projekty.  
  
 [Rozšíření dalších částí sady Visual Studio](../../extensibility/extending-other-parts-of-visual-studio.md)  
 Vysvětluje, jak používat [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] services k vytvoření prvky uživatelského rozhraní, které odpovídají zbytek [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].