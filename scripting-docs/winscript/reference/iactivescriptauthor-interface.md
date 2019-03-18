---
title: IActiveScriptAuthor Interface | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptAuthor interface
ms.assetid: df1f454d-01ee-4beb-928b-48513d07365a
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6b3d9725d72f5213aadc3d9400bef87cecb20ba0
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58159293"
---
# <a name="iactivescriptauthor-interface"></a>IActiveScriptAuthor – rozhraní
Představuje objekt pro vytváření služeb, včetně technologie IntelliSense a kolaci informace.  
  
 Kromě metod zděděných z `IUnknown`, `IActiveScriptAuthor` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IActiveScriptAuthor::AddNamedItem](../../winscript/reference/iactivescriptauthor-addnameditem.md)|Přidá název položky kořenové úrovně skriptu pro vytváření oboru názvů vyhledávacího stroje. A *kořenovou položku* je objekt obsahující vlastnosti a metody a mohou obsahovat také zdroj událostí.|  
|[IActiveScriptAuthor::AddScriptlet](../../winscript/reference/iactivescriptauthor-addscriptlet.md)|Přidá skriptlet kódu jako podřízený objekt úrovni kořenového adresáře `IScriptNode` objektu. Na hostiteli plně kvalifikovaný název skriptletu může mít pouze dvě úrovně.|  
|[IActiveScriptAuthor::AddTypeLib](../../winscript/reference/iactivescriptauthor-addtypelib.md)|Přidá knihovnu typů do oboru skriptu.|  
|[IActiveScriptAuthor::GetChars](../../winscript/reference/iactivescriptauthor-getchars.md)|Vrátí sadu znaků dokončení pro dokončení požadované kontext.|  
|[IActiveScriptAuthor::GetEventHandler](../../winscript/reference/iactivescriptauthor-geteventhandler.md)|Vrátí skriptletu, který má zadané atributy.|  
|[IActiveScriptAuthor::GetInfoFromContext](../../winscript/reference/iactivescriptauthor-getinfofromcontext.md)|Vrátí zadejte informace a pozice ukotvení pro daný znak do bloku kódu. To poskytuje informace pro člena, technologie IntelliSense, globální seznamy a tipy pro parametr.|  
|[IActiveScriptAuthor::GetLanguageFlags](../../winscript/reference/iactivescriptauthor-getlanguageflags.md)|Vrátí informace o jazyce.|  
|[IActiveScriptAuthor::GetRoot](../../winscript/reference/iactivescriptauthor-getroot.md)|Vrátí `IScriptNode` kořen stromu skript autora.|  
|[IActiveScriptAuthor::GetScriptletTextAttributes](../../winscript/reference/iactivescriptauthor-getscriptlettextattributes.md)|Vrací atributy textu skriptletu.|  
|[IActiveScriptAuthor::GetScriptTextAttributes](../../winscript/reference/iactivescriptauthor-getscripttextattributes.md)|Vrátí text atributy blok skriptu.|  
|[IActiveScriptAuthor::IsCommitChar](../../winscript/reference/iactivescriptauthor-iscommitchar.md)|Vrátí hodnotu určující, zda daný znak měli potvrdit dokončování příkazů aplikací.|  
|[IActiveScriptAuthor::ParseScriptText](../../winscript/reference/iactivescriptauthor-parsescripttext.md)|Analyzuje text skriptu, přidá text pro vytváření skriptu pro vytváření modulu a vytvoří `IScriptEntry` objekt, který odpovídá bloku skriptu.|  
|[IActiveScriptAuthor::RemoveNamedItem](../../winscript/reference/iactivescriptauthor-removenameditem.md)|Odebere `NamedItem` objektů z oboru názvů skript, modul pro vytváření.|  
|[IActiveScriptAuthor::RemoveTypeLib](../../winscript/reference/iactivescriptauthor-removetypelib.md)|Odebere ze skriptu pro vytváření oboru názvů modul knihovny typů.|  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní pro vytváření aktivních skriptů](../../winscript/reference/active-script-authoring-interfaces.md)