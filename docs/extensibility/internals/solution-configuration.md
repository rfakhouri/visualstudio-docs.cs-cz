---
title: "Konfigurace řešení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: solution configurations
ms.assetid: f22cfc75-3e31-4e0d-88a9-3ca99539203b
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5b9009a4adab2420a796b3011175ef37fac9bfcb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="solution-configuration"></a>Konfigurace řešení
Konfigurace řešení úložiště vlastnosti na úrovni řešení. Jejich přímé chování **spustit** klíč (F5) a **sestavení** příkazy. Ve výchozím nastavení tyto příkazy sestavit a spustit konfiguraci ladění. Oba příkazy spustí v kontextu konfigurace řešení. To znamená, že uživatel očekávat F5 start a sestavení bez ohledu aktivním řešení se konfigurují prostřednictvím nastavení. Prostředí je určena k optimalizaci pro řešení, nikoli projekty, pokud jde o vytváření a spouštění.  
  
 Standardním panelu nástrojů Visual Studio obsahuje tlačítko Start a konfigurace řešení rozevíracího seznamu vedle tlačítka Start. Tento seznam umožňuje uživatelům zvolit konfiguraci spustit při stisknutí klávesy F5, vytvořit své vlastní konfigurace řešení nebo upravit stávající konfigurace.  
  
> [!NOTE]
>  Neexistují žádné rozhraní rozšíření k vytvoření nebo úpravě konfigurace řešení. Je nutné použít `DTE.SolutionBuilder`. Existují však rozšiřitelnost rozhraní API pro správu sestavení řešení. Další informace naleznete v tématu <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionBuildManager2>.  
  
 Zde je, jak můžete implementovat konfigurace řešení nepodporuje typ vašeho projektu:  
  
-   Project  
  
     Zobrazuje názvy projektů v aktuálním řešení nalezen.  
  
-   Konfigurace  
  
     Zadejte seznam konfigurace nepodporuje typ vašeho projektu a zobrazit na stránkách vlastností implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2>.  
  
     Sloupec konfigurace zobrazí název konfigurace projektu k sestavení v této konfiguraci řešení a zobrazí seznam všech konfigurace projektu klepnutím na tlačítko se šipkou. Volání prostředí <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2.GetCfgNames%2A> metoda k vyplnění tohoto seznamu. Pokud <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2.GetCfgProviderProperty%2A> metoda znamená, že projekt podporuje úpravu konfigurace nové nebo upravit možnosti se také zobrazí v části konfigurace. Všechny tyto možnosti spuštění dialogových oken, které volají metody `IVsCfgProvider2` rozhraní pro úpravy konfigurace projektu.  
  
     Pokud projekt nepodporuje konfigurace, sloupci konfigurace žádný zobrazí a je zakázaná.  
  
-   Platforma  
  
     Zobrazí platformy sestavení pro konfigurace vybrané projektu a uvádí všechny dostupné platformy pro projekt klepnutím na tlačítko se šipkou. Volání prostředí <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2.GetPlatformNames%2A> metoda k vyplnění tohoto seznamu. Pokud <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2.GetCfgProviderProperty%2A> metoda označuje, že projekt podporuje platformy úpravy, nové nebo upravit možnosti jsou také zobrazeným pod záhlavím platformy. Všechny tyto možnosti spuštění dialogových oken, které volají `IVsCfgProvider2` metody upravit dostupné platformy projektu.  
  
     Pokud projekt nepodporuje platformy, sloupci platformy pro tento projekt žádný zobrazí a je zakázaná.  
  
-   Sestavení  
  
     Určuje, zda aktuální řešení konfigurace sestavení projektu. Nezaškrtnuté projekty nejsou vytvořené při sestavení řešení úrovni příkazy jsou vyvolány i přes všechny závislosti projektu, která obsahují. Není vybrán má být sestaven projekty jsou stále součástí ladění, spouštění, balení a nasazení řešení.  
  
-   Nasazení  
  
     Určuje, zda bude projekt nasazen při počáteční nebo nasadit příkazy jsou použitá s konfigurací sestavení vybraného řešení. Zaškrtněte políčko u tohoto pole bude k dispozici, pokud projekt podporuje nasazení implementací <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployableProjectCfg> rozhraní na jeho <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg2> objektu.  
  
 Jakmile se přidá novou konfiguraci řešení, kterého uživatel může vybrat z rozevíracího seznamu pole konfigurace řešení na standardním panelu nástrojů na sestavení nebo spusťte pro tuto konfiguraci.  
  
## <a name="see-also"></a>Viz také  
 [Správa možnosti konfigurace](../../extensibility/internals/managing-configuration-options.md)   
 [Konfigurace projektu pro vytváření](../../extensibility/internals/project-configuration-for-building.md)   
 [Objekt konfigurace projektu](../../extensibility/internals/project-configuration-object.md)