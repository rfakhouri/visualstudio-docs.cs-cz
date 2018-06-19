---
title: Konfigurace projektu pro správu nasazení | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project configurations, managing deployment
- projects [Visual Studio SDK], configuration for managing deployment
ms.assetid: bd5940d9-d94d-4944-beda-4ec1ab2bbde5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 723edd078636eb324fc2d5dfca2ae81ef3249a43
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31132247"
---
# <a name="project-configuration-for-managing-deployment"></a>Konfigurace projektu pro správu nasazení
Nasazení je v rámci fyzickým přesunutím položky výstup z procesu sestavení do očekávaného umístění pro ladění a instalaci. Například webové aplikace může vytvořené v místním počítači a pak umístit na serveru.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] podporuje dva způsoby, jak projekty může být součástí nasazení:  
  
-   Jako předmět procesu nasazení.  
  
-   Jako správce procesu nasazení.  
  
 Předtím, než mohou být nasazeny řešení, je nejprve nutno přidat projektu nasazení a konfigurovat možnosti nasazení. Pokud projekt nasadit již neexistuje, budete dotázáni, zda chcete vytvořit při výběru **nasadit řešení** z **sestavení** nabídky nebo klikněte pravým tlačítkem na řešení. Kliknutím na tlačítko **Ano** otevře **přidat nový projekt** dialogové okno s **vzdáleného Průvodce nasazením** projekt vybraný.  
  
 Průvodce nasazením vzdáleného žádostí pro typ aplikace (Windows nebo webu), skupiny výstupu projektu zahrnout, případných dalších souborů, které chcete zahrnout a vzdálený počítač, který chcete nasadit. Na poslední stránku průvodce zobrazí shrnutí vybrané možnosti.  
  
 Projekty, které jsou předmětem procesu nasazení vytvořit výstupní položky, které je třeba přesunout do alternativní prostředí. Tyto výstupní položky jsou popsány jako parametry pro <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg2> rozhraní, jejichž primární účel Pokud umožňující projekty tak, aby skupina výstupy. Další informace týkající se implementace `IVsProjectCfg2`, najdete v části [konfigurace projektu pro výstup](../../extensibility/internals/project-configuration-for-output.md).  
  
 Projekty nasazení, které umožňuje spravovat proces nasazení, povolte příkaz nasadit a reagovat, když je vybraný tento příkaz. Projekty nasazení implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployableProjectCfg> rozhraní pro provádění nasazení a provádět volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployStatusCallback> rozhraní do sestavy nasazení události stavu.  
  
 Konfigurace můžete určit závislosti, které ovlivňují činnosti sestavení nebo nasazení. Vytvořit nebo nasadit závislosti jsou projekty, které musí být buď vytvořené nebo nasadit před nebo po konfiguraci sami jsou vytvořené nebo nasadit. Sestavení závislosti mezi projekty jsou popsány se <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildDependency> rozhraní a nasadit závislosti s <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployDependency> rozhraní. Další informace najdete v tématu [konfigurace projektu pro vytvoření](../../extensibility/internals/project-configuration-for-building.md).  
  
## <a name="see-also"></a>Viz také  
 [Správa možnosti konfigurace](../../extensibility/internals/managing-configuration-options.md)   
 [Konfigurace projektu pro vytváření](../../extensibility/internals/project-configuration-for-building.md)   
 [Konfigurace projektu pro výstup](../../extensibility/internals/project-configuration-for-output.md)