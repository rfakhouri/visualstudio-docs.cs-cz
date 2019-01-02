---
title: Používání a poskytování služeb | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- examples [Visual Studio SDK], services
- Visual Studio, services
- services
ms.assetid: c0b415ba-b825-4da0-9faf-8a60a663e302
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f547afd33166a6a7b10284e6cb55e73baeefc861
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53886277"
---
# <a name="using-and-providing-services"></a>Používání a poskytování služeb
Služba je kontrakt mezi dvěma rozšíření VSPackages. Jeden VSPackage nabízí konkrétní sadu rozhraní pro jiné VSPackage využívat. Například [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nabízí <xref:Microsoft.VisualStudio.Shell.Interop.SVsActivityLog> služby žádné VSPackage jeho zatížení. Tato služba poskytuje <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog> rozhraní, které lze použít k zápisu do protokolu aktivit. Další informace najdete v tématu [jak: Použití protokolu aktivit](../extensibility/how-to-use-the-activity-log.md).  
  
 Rozšíření VSPackages můžete nabízet služby jejich vlastní použití <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService> rozhraní...  
  
 Visual Studio nabízí důležité služby, jako je následující:  
  
|Služba na integrované vývojové prostředí|Popis|  
|-----------------|-----------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>|Poskytuje přístup k integrované vývojové prostředí služby práci s základní funkce, rozšíření VSPackages a registru.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>|Poskytuje základní oddílová a související s Uživatelským rozhraním funkce v rozhraní IDE, jako je například schopnost vytvářet nástroje a oken s dokumentem.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution>|Poskytuje základní funkce týkající se řešení, jako je například možnost udělat výčet projektů, vytvořit nové projekty a sledovat změny v projektu.|  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Základy služeb](../extensibility/internals/service-essentials.md)  
 Uvede počet důležité elementy služby Visual Studio.  
  
 [Postupy: Získání služby](../extensibility/how-to-get-a-service.md)  
 Popisuje, jak požádat o (spotřebovávat) služby.  
  
 [Postupy: Poskytování služeb](../extensibility/how-to-provide-a-service.md)  
 Popisuje, jak poskytovat služby.  
  
 [Postupy: Zadejte službu asynchronní aplikace Visual Studio](../extensibility/how-to-provide-an-asynchronous-visual-studio-service.md)  
 Popisuje, jak k poskytování asynchronní služby.  
  
 [Postupy: Odstraňování potíží se službami](../extensibility/how-to-troubleshoot-services.md)  
 Tento článek popisuje běžné problémy a nabídne řešení k nim.  
  
## <a name="related-sections"></a>Související oddíly  
 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)