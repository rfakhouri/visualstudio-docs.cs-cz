---
title: Výběr objektů kontextu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- selection, tracking
- selection, context objects
ms.assetid: 7308ea8f-a42c-47e5-954e-7dee933dce7a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 04ccc4a57ac7af144c134761119433b7533e9bec
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="selection-context-objects"></a>Výběr objektů kontextu
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Integrované vývojové prostředí (IDE) používá k určení, co má být zobrazena v prostředí IDE objekt kontextu globální výběr. Každý okna v prostředí IDE může mít svůj vlastní objekt kontextu výběr nabídnutých do kontextu globální výběr. Prostředí IDE aktualizuje kontext globální výběr hodnoty z okna při toto okno je aktivní. Další informace najdete v tématu [zpětnou vazbu pro uživatele](../../extensibility/internals/feedback-to-the-user.md).  
  
 Každý rámec okna nebo lokalita v prostředí IDE má služba s názvem <xref:Microsoft.VisualStudio.Shell.Interop.STrackSelection>. Objekt vytvořený vaší VSPackage, který je umístěný v rámce okna musí volat `QueryService` Metoda získání ukazatele na <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection> rozhraní.  
  
 Okna s rámečkem můžete ponechat části jejich výběr kontextové informace z nebyl rozšířen do globální výběr kontextu, když jsou spuštěny. Tato možnost je užitečná pro nástroj windows, které může být nutné začít s prázdnou výběr.  
  
 Úpravy globální výběr kontextu aktivačních událostí události, které můžete sledovat VSPackages. VSPackages můžete provádět následující úlohy implementací `IVsTrackSelectionEx` a <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection> rozhraní:  
  
-   Aktualizujte aktuálně aktivní soubor v hierarchii.  
  
-   Sledování změn pro určité typy elementů. Například, pokud vaše VSPackage používá speciální **vlastnosti** okno, můžete sledovat změny v aktivním **vlastnosti** okno a znovu spusťte váš vyžádání.  
  
 Následující pořadí ukazuje typické během výběr pro sledování.  
  
1.  Prostředí IDE načte kontext výběr z okna nově otevřené a vloží ho v kontextu globální výběr. Pokud kontext výběr používá HIERARCHY_DONTPROPAGATE nebo SELCONTAINER_DONTPROPAGATE, tyto informace se rozšíří do globálním kontextu. Další informace najdete v tématu [zpětnou vazbu pro uživatele](../../extensibility/internals/feedback-to-the-user.md).  
  
2.  Události oznámení jsou všesměrové vysílání pro všechny VSPackage, který je požadovaný.  
  
3.  VSPackage funguje na události, které obdrží provedením aktivity, například aktualizace hierarchie, opětovné aktivaci nástroj nebo jiné podobné úlohy.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection>   
 [Hierarchie v sadě Visual Studio](../../extensibility/internals/hierarchies-in-visual-studio.md)   
 [Výběr a měny v prostředí IDE](../../extensibility/internals/selection-and-currency-in-the-ide.md)   
 [Typy projektů](../../extensibility/internals/project-types.md)