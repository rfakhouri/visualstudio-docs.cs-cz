---
title: Vytváření složek nadřazený kontejnerů pro řešení | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- solutions, creating parent containers
- source control plug-ins, creating parent containers
ms.assetid: 961e68ed-2603-4479-a306-330eda2b2efa
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d50800e527c6e79100bf699172f7fc30881b3299
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66332736"
---
# <a name="create-parent-container-folders-for-solutions"></a>Vytvoření nadřazené složky kontejneru pro řešení
Ve verzi 1.2 zdrojového ovládacího prvku modulu Plug-in rozhraní API můžete uživatele zadejte cílovou složku jeden kořenový zdrojového ovládacího prvku pro všechny webové projekty v řešení. Tento jeden kořenový se nazývá Super Unified Root (SUR).

 Do zdrojového ovládacího prvku modulu Plug-in API verze 1.1 Pokud uživatel přidán multiprojektová řešení do správy zdrojového kódu se uživatel vyzván a zadejte jednu cílovou složku zdrojového ovládacího prvku pro každý webový projekt.

## <a name="new-capability-flags"></a>Nové příznaky funkcí
 `SCC_CAP_CREATESUBPROJECT`

 `SCC_CAP_GETPARENTPROJECT`

## <a name="new-functions"></a>Nové funkce
- [SccCreateSubProject](../../extensibility/scccreatesubproject-function.md)

- [SccGetParentProjectPath](../../extensibility/sccgetparentprojectpath-function.md)

 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE vytvoří složku SUR téměř vždy, když přidání řešení do správy zdrojového kódu. Konkrétně provádí se v následujících případech:

- Projekt je projekt webové sdílené složky souborů.

- Existují různé jednotky pro projekt a soubor řešení.

- Existují jiné sdílené složky pro projekt a soubor řešení.

- Projekty byly přidány samostatně (v řešení se spravovanými zdroji).

V [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], doporučuje se, že název složky SUR být stejný jako název řešení bez přípony. Následující tabulka shrnuje chování v obou verzích.

|Funkce|Zdroj modulu Plug-in API správy ve verzi 1.1|Zdroj modulu Plug-in API správy ve verzi 1.2|
|-------------| - | - |
|Přidat řešení do SCC|SccInitialize()<br /><br /> SccGetProjPath()<br /><br /> SccGetProjPath()<br /><br /> SccOpenProject()|SccInitialize()<br /><br /> SccGetProjPath()<br /><br /> SccCreateSubProject()<br /><br /> SccCreateSubProject()<br /><br /> SccOpenProject()|
|Přidat projekt do řešení se spravovanými zdroji|SccGetProjPath()<br /><br /> OpenProject()|SccGetParentProjectPath()<br /><br /> SccOpenProject()<br /><br />  **Poznámka:**  Visual Studio předpokládá, že řešení je přímý podřízený sursaft|

## <a name="examples"></a>Příklady
 V následující tabulce jsou uvedeny dva příklady. V obou případech [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] uživatel je vyzván k zadání cílové umístění pro řešení pod správou zdrojového kódu až *user_choice* je zadán jako cíl. Je-li user_choice zadána, jsou přidány dva projekty a řešení bez výzvy k zadání cíle ovládacího prvku zdroje.

|Řešení obsahuje|Na umístění disku|Struktury výchozí databáze|
|-----------------------|-----------------------|--------------------------------|
|*sln1.sln*<br /><br /> Web1<br /><br /> Web2|*C:\Solutions\sln1*<br /><br /> *C:\Inetpub\wwwroot\Web1*<br /><br /> \\\server\wwwroot$\Web2|$/<user_choice>/sln1<br /><br /> $/<user_choice>/C/Web1<br /><br /> $/<user_choice>/Web2|
|*sln1.sln*<br /><br /> Web1<br /><br /> Win1|*C:\Solutions\sln1*<br /><br /> *D:\Inetpub\wwwroot\Web1*<br /><br /> *C:\solutions\sln1\Win1*|$/<user_choice>/sln1<br /><br /> $/<user_choice>/D/web1<br /><br /> $/<user_choice>/sln1/win1|

 Bez ohledu na to, zda operace je zrušená nebo se nepovedlo kvůli chybě se vytvoří SUR složce a jejích podsložkách. Nejsou odebrány automaticky v zrušit nebo chybové podmínky.

 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] použije výchozí chování verze 1.1, pokud modul plug-in správy zdrojového kódu nevrací `SCC_CAP_CREATESUBPROJECT` a `SCC_CAP_GETPARENTPROJECT` příznaky funkcí. Kromě toho uživatelům [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] můžete vrátit k verzi 1.1 chování tak, že nastavíte hodnotu následující klíč do *DWORD: 00000001*:

 **[HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl] DoNotCreateSolutionRootFolderInSourceControl** = *dword:00000001*

## <a name="see-also"></a>Viz také:
- [Co je nového v zdrojový ovládací prvek modulu Plug-in API verze 1.2](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)