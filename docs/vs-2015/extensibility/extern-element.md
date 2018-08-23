---
title: Extern – Element | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Extern
helpviewer_keywords:
- VSCT XML schema elements, Extern
- Extern element (VSCT XML schema)
ms.assetid: db6c3ddd-a1ba-450a-897a-bb568a5377fc
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5dce51835164424272874b42b6073131607c7272
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42676966"
---
# <a name="extern-element"></a>Extern – element
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [Extern – Element](https://docs.microsoft.com/visualstudio/extensibility/extern-element).  
  
Extern element odkazuje na všechny soubory externích záhlaví (.h) ke sloučení s souboru .vsct v době kompilace. Soubory, které chcete sloučit, musí být na cesty zahrnutí zadaný pro kompilátor VSCT nebo odkazuje [Include Element](../extensibility/include-element.md). Soubory může být jiné .vsct soubory nebo soubory hlaviček jazyka C++.  
  
 Definice v souborech hlaviček musí být ve formátu "#define [Symbol] [hodnota]" hodnota může být další symbol, pokud je již definován. Podmíněné příkazy příkaz položek lze definice. Jakýkoli symbol doopravdy nepoužije se zahodí.  
  
 CommandTable – element  
Extern – element  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<Extern href="stdidcmd.h" />  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|href|Požadováno. Cesta k souboru hlaviček:<br /><br /> href="stdidcmd.h"|  
|Podmínka|Volitelné. Zobrazit [podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
|jazyk|Volitelné. Výchozí jazyk všech [ \<řetězce >](../extensibility/strings-element.md) elementy v tabulce příkazu:<br /><br /> jazyk = "en-us"|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|Žádné|Žádné|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[CommandTable – element](../extensibility/commandtable-element.md)|Definuje všechny prvky, které představují příkazy – to znamená, položek nabídky, nabídky, panely nástrojů a pole se seznamem – poskytující VSPackage rozhraní IDE.|  
  
## <a name="example"></a>Příklad  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-  
  18/CommandTable" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <Extern href="C:\VSCore\vscommon\inc\vsshlids.h"/>  
    …  
  <Commands package="guidMyPackage">  
</CommandTable>  
```  
  
## <a name="see-also"></a>Viz také  
 [Tabulky příkazů sady Visual Studio (. Soubory Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [Jak balíčky VSPackages přidávají prvky uživatelského rozhraní](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Příkazy, nabídky a panely nástrojů](../extensibility/internals/commands-menus-and-toolbars.md)

