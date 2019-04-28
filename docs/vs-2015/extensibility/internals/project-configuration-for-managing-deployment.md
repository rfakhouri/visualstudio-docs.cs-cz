---
title: Konfigurace projektu pro správu nasazení | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project configurations, managing deployment
- projects [Visual Studio SDK], configuration for managing deployment
ms.assetid: bd5940d9-d94d-4944-beda-4ec1ab2bbde5
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: d5b16c3392e9432ba540130d45f6907de15b51ab
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62429948"
---
# <a name="project-configuration-for-managing-deployment"></a>Konfigurace projektu pro správu nasazení
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nasazení se v rámci fyzickým přesunutím položek výstup z procesu sestavení do očekávaného umístění pro ladění a instalaci. Například webové aplikace může být založená na místním počítači a pak umístit na serveru.  
  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] podporuje dva způsoby, které projekty mohou být součástí nasazení:  
  
- Jako subjekt proces nasazení.  
  
- Jako správce procesu nasazení.  
  
  Předtím, než je možné nasadit řešení, musíte nejprve přidat projekt nasazení konfigurovat možnosti nasazení. Pokud projekt nasadit ještě neexistuje, zobrazí se výzva, pokud chcete jeden vytvořit, když vyberete **nasadit řešení** z **sestavení** nabídku nebo klikněte pravým tlačítkem řešení. Kliknutím na **Ano** otevře **přidat nový projekt** dialogové okno s **Průvodce vzdáleným nasazení** vybraný projekt.  
  
  Průvodce vzdáleným nasazení vyzve k typu aplikace (Windows nebo Web), výstupní skupiny projektů zahrnout, všechny další soubory, které chcete zahrnout a vzdáleného počítače, který chcete nasadit do. Na poslední stránce Průvodce zobrazí souhrn vybraných možností.  
  
  Projekty, které jsou předmětem proces nasazení vytvoří výstupní položky, které musí být přesunuty do alternativní prostředí. Tyto výstupní položky jsou popsány jako parametry <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg2> rozhraní, jejichž primární účel if povolit projektů do skupiny výstupů. Další informace týkající se provádění `IVsProjectCfg2`, naleznete v tématu [konfigurace projektu pro výstup](../../extensibility/internals/project-configuration-for-output.md).  
  
  Projekty nasazení, které spravovat proces nasazení, povolit příkaz nasazení a odpovědět při výběru tohoto příkazu. Implementace projektů nasazení <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployableProjectCfg> k provedení nasazení a provádět volání do rozhraní <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployStatusCallback> nasazení rozhraní k sestavě stav události.  
  
  Konfigurace můžete určit závislosti, které by ovlivnily provoz jejich sestavení nebo nasazení. Vytvoření buildu nebo nasazení závislosti jsou projekty, které musí buď být sestavuje nebo nasazuje před nebo po se sestavuje nebo nasazuje konfigurace sami. Závislosti sestavení mezi projekty jsou popsané společně s <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildDependency> rozhraní a nasadit závislosti s <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployDependency> rozhraní. Další informace najdete v tématu [konfigurace projektu pro sestavení](../../extensibility/internals/project-configuration-for-building.md).  
  
## <a name="see-also"></a>Viz také  
 [Správa možností konfigurace](../../extensibility/internals/managing-configuration-options.md)   
 [Konfigurace projektu pro sestavení](../../extensibility/internals/project-configuration-for-building.md)   
 [Konfigurace projektu pro výstup](../../extensibility/internals/project-configuration-for-output.md)
