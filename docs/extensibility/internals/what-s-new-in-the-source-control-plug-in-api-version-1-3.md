---
title: Co&#39;nového ve zdroji ovládací prvek modulu Plug-in API ve verzi 1.3 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, what's new in API v1.3
- what's new [Visual Studio SDK], source control plug-ins
ms.assetid: 7dfb2227-6e1d-4028-bce9-f8967456a993
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: df93626066441226e7f41963e60e3417e8cc12da
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66323107"
---
# <a name="what39s-new-in-the-source-control-plug-in-api-version-13"></a>Co&#39;nového ve zdroji ovládací prvek modulu Plug-in API ve verzi 1.3
Rozhraní API modulu Plug-in zdroje ovládacího prvku verze 1.3 zavádí následující nové funkce k poskytování pokročilé řízení.

## <a name="changes"></a>Změny
 Rozhraní API modulu Plug-in zdroje ovládacího prvku verze 1.3 přibyly následující funkce:

|Funkce|Přehled|
|--------------|--------------|
|[SccGetExtendedCapabilities](../../extensibility/sccgetextendedcapabilities-function.md)|Umožňuje další možnosti bits, aby oznámený|
|[SccEnumChangedFiles](../../extensibility/sccenumchangedfiles-function.md)|Umožňuje zkoumání souborů, které mají novější verze v databázi správy verzi než na místním disku|
|[SccQueryChanges](../../extensibility/sccquerychanges-function.md)|Zadané soubory umožňují zkoumání stavu změny názvu (přejmenování, přidání a odstranění)|
|[SccPopulateDirList](../../extensibility/sccpopulatedirlist-function.md)|Umožňuje zkoumání adresářů a souborů v databázi správy verzí|
|[SccAddFilesFromSCC](../../extensibility/sccaddfilesfromscc-function.md)|Přidá zadaný seznam souborů z databází správy verzí do aktuálního projektu|
|[SccBackgroundGet](../../extensibility/sccbackgroundget-function.md)|Provádí bezobslužné "Get" zadaných souborů (bez uživatelského rozhraní se zobrazí)|
|[SccGetUserOption](../../extensibility/sccgetuseroption-function.md)|Umožňuje přístup k možnosti specifické pro uživatele|

## <a name="see-also"></a>Viz také
- [Začínáme](../../extensibility/internals/getting-started-with-source-control-plug-ins.md)
- [Co je nového v rozhraní API modulu plug-in správy zdrojového kódu ve verzi 1.2](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)