---
title: "Jaký & č. 39; s ve zdroji řízení verze rozhraní API modulu Plug-in 1.3 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control plug-ins, what's new in API v1.3
- what's new [Visual Studio SDK], source control plug-ins
ms.assetid: 7dfb2227-6e1d-4028-bce9-f8967456a993
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: bd0c23258034fb99f5e2e4e0c86ca9e61c3d68ab
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="what39s-new-in-the-source-control-plug-in-api-version-13"></a>Jaký & č. 39; s nové v zdroj ovládacího prvku modulu Plug-in verze rozhraní API 1.3
Zdroj ovládacího prvku Plug-in API verze 1.3 zavádí následující nové funkce k poskytování pokročilejší řízení.  
  
## <a name="changes"></a>Změny  
 Zdroj ovládacího prvku Plug-in API verze 1.3 přibyly následující funkce:  
  
|Funkce|Přehled|  
|--------------|--------------|  
|[SccGetExtendedCapabilities](../../extensibility/sccgetextendedcapabilities-function.md)|Povoluje další funkce bits, aby byly hlášené|  
|[SccEnumChangedFiles](../../extensibility/sccenumchangedfiles-function.md)|Umožňuje zkoumání souborů, které mají novější verze v databázi řízení verze než na místním disku|  
|[SccQueryChanges](../../extensibility/sccquerychanges-function.md)|Umožňuje prozkoumání stavu změny názvu (přejmenování, přidání a odstranění) pro zadané soubory|  
|[SccPopulateDirList](../../extensibility/sccpopulatedirlist-function.md)|Umožňuje prozkoumání adresářů a souborů v databázi verze ovládacího prvku|  
|[SccAddFilesFromSCC](../../extensibility/sccaddfilesfromscc-function.md)|Přidá zadaný seznam souborů z verze databáze ovládacího prvku do aktuálního projektu|  
|[SccBackgroundGet](../../extensibility/sccbackgroundget-function.md)|Provede tichou "Get" zadané soubory (zobrazené žádné uživatelské rozhraní)|  
|[SccGetUserOption](../../extensibility/sccgetuseroption-function.md)|Umožňuje přístup k možnosti specifické pro uživatele|  
  
## <a name="see-also"></a>Viz také  
 [Začínáme](../../extensibility/internals/getting-started-with-source-control-plug-ins.md)   
 [Co je nového v zdroj ovládacího prvku modulu Plug-in rozhraní API verze 1.2](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)