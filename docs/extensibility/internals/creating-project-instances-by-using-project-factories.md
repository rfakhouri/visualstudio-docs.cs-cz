---
title: "Vytváření instancí projektu pomocí objekty pro vytváření projektů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project factories
- projects [Visual Studio SDK], project factories
ms.assetid: 94c90012-8669-459c-af8e-307ac242c8c4
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7175bd4e2d0b07640dd45b38aa246c649def32ef
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="creating-project-instances-by-using-project-factories"></a>Vytváření instancí projektu pomocí objekty pro vytváření projektů
Typy v projektu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] používat *vytváření projektu* k vytvoření instancí objektů projektu. Objekt pro vytváření projektu je podobná objekt standardní třídu pro cocreatable COM – objekty. Objekty projektu však nejsou cocreatable: jejich lze vytvořit pouze pomocí objekt pro vytváření projektu.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE volání objektu pro vytváření projektu v vaší VSPackage implementovat, pokud uživatel načítá existujícího projektu nebo vytvoří nový projekt v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Nový objekt projektu poskytuje IDE s dostatek informací k naplnění Průzkumníku řešení. Nový objekt projektu také poskytuje požadované rozhraní pro podporu všech příslušných akcí uživatelského rozhraní iniciovaná rozhraní IDE.  
  
 Můžete implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory> rozhraní v třídě ve vašem projektu. Obvykle se nachází v jeho vlastní modul.  
  
 Příklad implementace `IVsProjectFactory` rozhraní najdete v tématu PrjFac.cpp, která je součástí [základního projektu](http://msdn.microsoft.com/en-us/385fd2a3-d9f1-4808-87c2-a3f05a91fc36) ukázka adresáře.  
  
 Projekty, které podporují agregovaný podle vlastníka musí zachovat klíčem vlastníka v jejich souboru projektu. Když <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CreateProject%2A> metoda je volána v projektu s klíčem vlastníka, která projektu převede jeho vlastníka klíč pro objekt pro vytváření projektu GUID pak zavolá `CreateProject` metodu na tomto projektu objektu pro vytváření provedete skutečné vytvoření.  
  
## <a name="creating-an-owned-project"></a>Vytvoření vlastní projektu  
 Vlastníka vytvoří vlastní projektu ve dvou fázích:  
  
1.  Při volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsOwnedProjectFactory.PreCreateForOwner%2A> metoda. Díky tomu vlastní projektu příležitosti k vytvoření objektu agregované projektu na základě vstupních řízení `IUnknown`. Vlastní projektu předá vnitřní `IUnknown` a agregovaný objekt zpět do vlastníka projektu. Díky tomu vlastní projektu příležitosti k uložení vnitřní `IUnknown`.  
  
2.  Při volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsOwnedProjectFactory.InitializeForOwner%2A> metoda. Vlastní projektu nemá všechny jeho vytváření instancí, když tato metoda je volána místo volání `IVsProjectFactory::CreateProject` jak by tomu bylo pro projekty, které nejsou vlastněny. Vstup `VSOWNEDPROJECTOBJECT` výčet je obvykle agregované vlastní projektu. Vlastní projektu tuto proměnnou můžete použít k určení, zda již bylo vytvořeno svého projektu objektu (soubor cookie se nerovná NULL) nebo musí být vytvořený (soubor cookie rovná NULL).  
  
 Typy projektů jsou označeny jedinečný identifikátor GUID, podobně jako CLSID cocreatable objektu COM projektu. Obvykle jeden projektu objekt pro vytváření obslužných rutin, vytváření instancí jedné projektu typu, i když je možné, že jeden objekt pro vytváření projektu zpracování více než jeden typ projektu identifikátor GUID.  
  
 Typy projektů jsou spojeny s konkrétní příponou názvu. Pokud se uživatel pokusí otevřít existující soubor projektu nebo pokusí o vytvoření nového projektu klonováním šablonu, rozhraní IDE používá rozšíření v souboru ke zjištění odpovídající projektu identifikátor GUID.  
  
 Jakmile IDE Určuje, jestli musíte vytvořit nový projekt nebo otevřít existující projekt určitého typu, rozhraní IDE používá informace v registru systému v části [HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\8.0\Projects] najít, což VSPackage implementuje objektu pro vytváření požadované projektu. Prostředí IDE načte tento VSPackage. V <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> metody VSPackage musí zaregistrovat jeho vytváření projektu pomocí rozhraní IDE voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterProjectTypes.RegisterProjectType%2A> metoda.  
  
 Primární metodou pro `IVsProjectFactory` rozhraní je <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CreateProject%2A> který pracovat ve dvou situacích: otevření existujícího projektu a vytvoření nového projektu. Většina projekty uložit jejich stavu projektu v souboru projektu. Obvykle jsou nové projekty vytvořené pomocí provádění předaný kopii souboru šablony `CreateProject` metoda a pak otevřete kopie. Existující projekty jsou mohl vytvořit jeho instanci přímo otevírání souboru projektu předaný `CreateProject` metoda. `CreateProject` Metoda můžete zobrazit další funkce uživatelského rozhraní pro uživatele podle potřeby.  
  
 Projekt můžete také použít žádné soubory a místo toho uložte stav projektu v mechanismus úložiště než systém souborů, jako je databáze nebo webový server. V takovém případě Předaný parametr názvu souboru `CreateProject` metoda není ve skutečnosti na cestu systému souborů, ale do jedinečného řetězce – adresa URL – k identifikaci dat projektu. Není potřeba kopírovat soubory šablon, které se předávají `CreateProject` k aktivaci odpovídající konstrukce pořadí spouštění.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsOwnedProjectFactory>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterProjectTypes>   
 [Kontrolní seznam: Vytvoření nové typy projektu](../../extensibility/internals/checklist-creating-new-project-types.md)