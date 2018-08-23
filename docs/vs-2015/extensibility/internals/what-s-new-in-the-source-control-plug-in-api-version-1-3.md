---
title: Co&#39;nového ve zdroji ovládací prvek modulu Plug-in API ve verzi 1.3 | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- source control plug-ins, what's new in API v1.3
- what's new [Visual Studio SDK], source control plug-ins
ms.assetid: 7dfb2227-6e1d-4028-bce9-f8967456a993
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d5e8e5fd761cbd8c1baf2b75160010f19a8430cc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42667714"
---
# <a name="what39s-new-in-the-source-control-plug-in-api-version-13"></a>Co&#39;nového ve zdroji ovládací prvek modulu Plug-in API ve verzi 1.3
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [co&#39;s nové verze 1.3 zdrojový ovládací prvek modulu Plug-in API](https://docs.microsoft.com/visualstudio/extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-3).  
  
Rozhraní API modulu Plug-in zdroje ovládacího prvku verze 1.3 zavádí následující nové funkce k poskytování pokročilé řízení.  
  
## <a name="changes"></a>Změny  
 Rozhraní API modulu Plug-in zdroje ovládacího prvku verze 1.3 přibyly následující funkce:  
  
|Funkce|Přehled|  
|--------------|--------------|  
|[Sccgetextendedcapabilities –](../../extensibility/sccgetextendedcapabilities-function.md)|Umožňuje další možnosti bits, aby oznámený|  
|[Sccenumchangedfiles –](../../extensibility/sccenumchangedfiles-function.md)|Umožňuje zkoumání souborů, které mají novější verze v databázi správy verzi než na místním disku|  
|[Sccquerychanges –](../../extensibility/sccquerychanges-function.md)|Zadané soubory umožňují zkoumání stavu změny názvu (přejmenování, přidání a odstranění)|  
|[Sccpopulatedirlist –](../../extensibility/sccpopulatedirlist-function.md)|Umožňuje zkoumání adresářů a souborů v databázi správy verzí|  
|[Sccaddfilesfromscc –](../../extensibility/sccaddfilesfromscc-function.md)|Přidá zadaný seznam souborů z databází správy verzí do aktuálního projektu|  
|[Sccbackgroundget –](../../extensibility/sccbackgroundget-function.md)|Provádí bezobslužné "Get" zadaných souborů (bez uživatelského rozhraní se zobrazí)|  
|[Sccgetuseroption –](../../extensibility/sccgetuseroption-function.md)|Umožňuje přístup k možnosti specifické pro uživatele|  
  
## <a name="see-also"></a>Viz také  
 [Začínáme se službou](../../extensibility/internals/getting-started-with-source-control-plug-ins.md)   
 [Co je nového v rozhraní API modulu plug-in správy zdrojového kódu ve verzi 1.2](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)

