---
title: "Podpora správy zdrojového kódu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: source control [Visual Studio SDK], supporting
ms.assetid: 567acde3-354e-4f39-8d99-0ef86c103396
caps.latest.revision: "18"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a93dbdff19d0a0feaafb549b00968e095690fd78
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="supporting-source-control"></a>Podpora správy zdrojového kódu
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]podporuje souboru rezervace, vrácení se změnami a jiných operací se zdrojovým ovládací prvek pro váš projekt nebo editor. Jako zdroj ovládacího prvku klienta [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] je navržen pro interakci s balíčkem řízení zdroje, jako například [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)], který poskytuje archivace, Správa verzí a řízení zařízení pro dynamicky definovanou sadu souborů.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Model pro balíčky zdroj ovládacího prvku](../../extensibility/internals/model-for-source-control-packages.md)  
 Popisuje typ projektu musí implementovat rozhraní pro podporu správy zdrojového kódu.  
  
 [Rozhodnutí o návrhu](../../extensibility/internals/source-control-design-decisions.md)  
 Poskytuje otázky, jejichž odpovědi změnit, jak implementovat typu projektu.  
  
 [Podrobnosti o konfiguraci](../../extensibility/internals/source-control-configuration-details.md)  
 Popisuje, jak podpora správy zdrojového kódu změní implementace typ projektu.  
  
 [Další pokyny pro projekty a editory](../../extensibility/internals/additional-source-control-guidelines-for-projects-and-editors.md)  
 Popisuje osvědčené postupy pro typy projektů a editory.  
  
 [Podrobnosti o modulu runtime](../../extensibility/internals/source-control-runtime-details.md)  
 Popisuje postup registrace projektu, pokud uživatel přidá do systému správy zdrojového kódu.  
  
## <a name="reference"></a>Odkaz  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>  
 Určuje prostředí nebo zdroj ovládacího prvku balíček, který soubor je Chystáte se změnit v paměti nebo uložený.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>  
 Umožňuje projekty a hierarchií zaregistrovat se správa zdrojového kódu a získat informace o řízení stav zdroje.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>  
 Implementované v systému projektu k zajištění správy zdrojového kódu pro soubory projektu a položky projektu.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>  
 Projekty používá k dotazování prostředí pro oprávnění k přidávání, odeberte nebo přejmenujte soubor nebo adresář v řešení.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>  
 Oznamuje klientům změny, které byly provedeny na projektu soubory nebo adresáře.  
  
## <a name="related-sections"></a>Související oddíly  
 [Typy projektů](../../extensibility/internals/project-types.md)  
 Poskytuje přehled projekty jako základní stavební bloky [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE). Jsou uvedeny odkazy na další témata, které vysvětlují, jak řídit projekty vytváření a kompilování kódu.