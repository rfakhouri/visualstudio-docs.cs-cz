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
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 36f49d4e1ebaa6d8e15e43b821af56204739cb07
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62798971"
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
- [Základy služby](../extensibility/internals/service-essentials.md) představuje důležité elementy služby Visual Studio.

- [Postupy: Získání služby](../extensibility/how-to-get-a-service.md) popisuje, jak požádat o (spotřebovávat) služby.

- [Postupy: Poskytování služeb](../extensibility/how-to-provide-a-service.md) pojednává o poskytování služeb.

- [Postupy: Poskytuje asynchronní služby Visual Studio](../extensibility/how-to-provide-an-asynchronous-visual-studio-service.md) popisuje, jak k poskytování asynchronní služby.

- [Postupy: Odstraňování potíží se službami](../extensibility/how-to-troubleshoot-services.md) popisuje běžné problémy a nabídne řešení k nim.

## <a name="related-sections"></a>Související oddíly
- [Visual Studio SDK](../extensibility/visual-studio-sdk.md)