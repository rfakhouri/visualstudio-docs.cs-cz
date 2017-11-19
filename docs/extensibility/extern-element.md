---
title: Extern Element | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Extern
helpviewer_keywords:
- VSCT XML schema elements, Extern
- Extern element (VSCT XML schema)
ms.assetid: db6c3ddd-a1ba-450a-897a-bb568a5377fc
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 764b6ff8b19711cb05f34c9bf652956057318346
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="extern-element"></a>Extern – Element
Extern element odkazuje na externí hlavičky () soubory sloučit s .vsct soubor v době kompilace. Soubory, který se má sloučit musí být na cestu zahrnutí zadané pro kompilátor VSCT nebo odkazuje [zahrnují Element](../extensibility/include-element.md). Soubory mohou být další .vsct soubory nebo soubory hlaviček C++.  
  
 Definice v záhlaví soubory musí být ve tvaru "#define [Symbol] [hodnota]" hodnota může být další symbol, pokud je definována dříve. Podmíněné příkazy položek příkaz je možné použít definice. Zahodí všechny symbolu používanou ve skutečnosti není.  
  
 CommandTable Element  
Extern – Element  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<Extern href="stdidcmd.h" />  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|href|Požadováno. Cesta k souboru hlavičky:<br /><br /> href="stdidcmd.h"|  
|Podmínka|Volitelné. V tématu [podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
|jazyk|Volitelné. Výchozí jazyk všech [ \<řetězce >](../extensibility/strings-element.md) prvky v tabulce příkaz:<br /><br /> jazyk = "en-us"|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|Žádné|Žádné|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[CommandTable Element](../extensibility/commandtable-element.md)|Definuje všechny elementy, které představují příkazy – to znamená, položky nabídky, nabídek, panely nástrojů a pole se seznamem – poskytující VSPackage k prostředí IDE.|  
  
## <a name="example"></a>Příklad  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-  
  18/CommandTable" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <Extern href="C:\VSCore\vscommon\inc\vsshlids.h"/>  
    ...  
  <Commands package="guidMyPackage">  
</CommandTable>  
```  
  
## <a name="see-also"></a>Viz také  
 [Visual Studio příkaz tabulky (. Soubory Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [Jak přidat VSPackages prvky uživatelského rozhraní](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Příkazy, nabídek a panelů nástrojů](../extensibility/internals/commands-menus-and-toolbars.md)