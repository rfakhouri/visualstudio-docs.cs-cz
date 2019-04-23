---
title: Upgrade položky projektu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: devlang-csharp
ms.topic: conceptual
helpviewer_keywords:
- upgrading project items
- projects [Visual Studio SDK], upgrading items
- project items [Visual Studio], upgrading
ms.assetid: 8af29dd4-eaf1-4b3c-b602-198e1a3dff23
caps.latest.revision: 14
manager: jillfra
ms.openlocfilehash: c07f8f62fb7ae84b5f3ee6140cccecf744c759e5
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60083917"
---
# <a name="upgrading-project-items"></a>Upgrade položky projektu
Je-li přidat nebo spravovat položky uvnitř systémů projektů, které neimplementuje, budete muset účastnit v procesu upgradu projektu. Crystal Reports je příklad položky, kterou lze přidat do projektu systému.  
  
 Obvykle implementátory položky projektu chcete využít již plně vytvořenou instanci a upgradovat projekt, protože potřebují vědět, jaké jsou odkazy na projekt a jaké jiné vlastnosti projektu jsou existuje pro rozhodnutí upgradu.  
  
### <a name="to-get-the-project-upgrade-notification"></a>Chcete-li získat oznámení o upgradu projektu  
  
1. Nastavte <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80.SolutionOrProjectUpgrading> příznak (definováno v vsshell80.idl) ve vaší implementaci položky projektu. To způsobí, že položky projektu VSPackage automaticky při načtení [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] prostředí zjistí, že bude systém projektu probíhá upgrade.  
  
2. Doporučte <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEventsProjectUpgrade> rozhraní prostřednictvím <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution2.AdviseSolutionEvents%2A> metoda.  
  
3. <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEventsProjectUpgrade> Rozhraní je aktivována po dokončení upgradu operací implementace systému projektu a je vytvořen nový upgradovaný projekt. V závislosti na scénáři <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEventsProjectUpgrade> rozhraní je aktivována po <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenSolution%2A>, <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenProject%2A>, nebo <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterLoadProject%2A> metody.  
  
### <a name="to-upgrade-the-project-item-files"></a>Upgradovat soubory položek projektu  
  
1. Proces zálohování souboru musíte pečlivě spravovat ve vaší implementaci položky projektu. To platí zejména pro zálohování vedle sebe, kde `fUpgradeFlag` parametr <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> metoda je nastavena na <xref:Microsoft.VisualStudio.Shell.Interop.__VSPPROJECTUPGRADEVIAFACTORYFLAGS>, kde jsou umístěny soubory, které se má zálohovat společně na straně soubory, které jsou označeny jako "old". Zálohované soubory starší než systémový čas, kdy byl projekt upgradovat, lze označit jako zastaralé. Kromě toho se může přepsat, pokud nebyla provést určité kroky, pokud tomu chcete zabránit.  
  
2. Položky projektu v době získá oznámení o upgrade projektu **Průvodce převodu Visual Studio** pořád zobrazuje. Proto měli používat metody <xref:Microsoft.VisualStudio.Shell.Interop.IVsUpgradeLogger> rozhraní kvůli upgradu zprávy do Průvodce vytvořením uživatelského rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [Průvodce převodu Visual Studio](http://msdn.microsoft.com/4acfd30e-c192-4184-a86f-2da5e4c3d83c)   
 [Upgrade vlastních projektů](../misc/upgrading-custom-projects.md)