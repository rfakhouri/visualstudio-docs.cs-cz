---
title: Podpora správy zdrojového kódu | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- source control [Visual Studio SDK], supporting
ms.assetid: 567acde3-354e-4f39-8d99-0ef86c103396
caps.latest.revision: 19
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 01941fdd4899142ae8abb96f57f93e3ebd0b6256
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42685104"
---
# <a name="supporting-source-control"></a>Podpora správy zdrojového kódu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [podpora správy zdrojového kódu](https://docs.microsoft.com/visualstudio/extensibility/internals/supporting-source-control).  
  
[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] podporuje souboru rezervace, vrácení se změnami a jiných operací správy zdrojů pro projekt nebo editoru. Jako zdrojový ovládací prvek klienta [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] je navržen pro interakci s balíčkem ovládací prvek zdroje, jako například [!INCLUDE[vsvss](../../includes/vsvss-md.md)], která poskytuje archivace, Správa verzí a řízení zařízení pro dynamicky definované sady souborů.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Model pro balíčky správy zdrojového kódu](../../extensibility/internals/model-for-source-control-packages.md)  
 Popisuje rozhraní, musí implementovat typ projektu pro podporu správy zdrojového kódu.  
  
 [Rozhodnutí o návrhu](../../extensibility/internals/source-control-design-decisions.md)  
 Obsahuje dotazy, jejichž odpovědi změnit, jak implementovat typ projektu.  
  
 [Podrobnosti o konfiguraci](../../extensibility/internals/source-control-configuration-details.md)  
 Popisuje, jak podpora správy zdrojového kódu se změní implementaci typu projektu.  
  
 [Další pokyny pro projekty a editory](../../extensibility/internals/additional-source-control-guidelines-for-projects-and-editors.md)  
 Tento článek popisuje osvědčené postupy pro typy projektů a editory.  
  
 [Podrobnosti modulu CLR](../../extensibility/internals/source-control-runtime-details.md)  
 Popisuje postup registrace projektu, když uživatel přidá do systému správy zdrojového kódu.  
  
## <a name="reference"></a>Odkaz  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>  
 Určuje prostředí nebo zdroj ovládacího prvku balíček, který soubor Chystáte se dá změnit v paměti nebo uložit.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>  
 Umožňuje projekty a hierarchie na zaregistrovat se správou zdrojového kódu a získávání informací o stav správy zdrojových kódů.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>  
 Implementováno v systému projektu k zajištění správy zdrojového kódu pro soubory projektu a položky projektu.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>  
 Chcete-li zadat dotaz na prostředí pro oprávnění, které chcete přidat, odebrat nebo přejmenovat soubor nebo adresář v řešení používá projekty.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>  
 Oznamuje klientům změny provedené na projektu soubory nebo adresáře.  
  
## <a name="related-sections"></a>Související oddíly  
 [Typy projektů](../../extensibility/internals/project-types.md)  
 Poskytuje přehled o projekty jako základní stavební bloky [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] integrované vývojové prostředí (IDE). Jsou uvedeny odkazy na další témata, která popisují, jak řídit projekty vytváření a kompilování kódu.

