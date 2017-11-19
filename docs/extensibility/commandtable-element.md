---
title: CommandTable Element | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CommandTable
helpviewer_keywords:
- CommandTable element (VSCT XML schema)
- VSCT XML schema elements, CommandTable
ms.assetid: 15c38159-660a-4ef4-9643-aa6fcfca82a9
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d4f1a906f545dcdbaefca7f5a38824a1f3259c97
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="commandtable-element"></a>CommandTable Element
CommandTable není kořenovým elementem .vsct souboru. Toto je soubor, který definuje skutečný rozložení a typ příkazů, které VSPackage poskytuje k prostředí IDE. Příkazy může zahrnovat položky nabídky, nabídek, panely nástrojů a pole se seznamem. Další informace najdete v tématu [tabulky příkaz Visual Studio (. Soubory Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable" xmlns:xs="http://www.w3.org/2001/XMLSchema" >  
  <Extern>... </Extern>  
  <Include>... </Include>  
  <Define>... </Define>  
  <Commands>... </Commands>  
  <CommandPlacements>... </CommandPlacements>  
  <VisibilityConstraints>... </VisibilityConstraints>  
  <KeyBindings>... </KeyBindings>  
  <UsedCommands... </UsedCommands>  
  <Symbols>... </Symbols>  
</CommandTable>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|atribut xmlns|Požadováno. Obory názvů XML:<br /><br /> atribut xmlns = "http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable"<br /><br /> xmlns:xs = "http://www.w3.org/2001/XMLSchema"|  
|jazyk|Volitelné. Atribut jazyk lze zadat výchozí jazyk všech \<řetězce > prvky v tabulce příkazu.  Pokud jazyk není zadán, použije se jazyk aktuální proces:<br /><br /> jazyk = "en-us"|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Extern – Element](../extensibility/extern-element.md)|Volitelné. Preprocesor – direktivy pro kompilátor obsahuje.|  
|[Zahrňte prvek](../extensibility/include-element.md)|Volitelné. Obsahuje cesty k souborům, které mají být zahrnuty kompilaci.|  
|[Definování elementu](../extensibility/define-element.md)|Volitelné. Definuje symbol daného jeho název a hodnotu.|  
|[Element příkazy](../extensibility/commands-element.md)|Volitelné. Definování všechny příkazy pro VSPackage, který obsahuje všechny další prvky nadřazeného elementu.|  
|[CommandPlacements Element](../extensibility/commandplacements-element.md)|Volitelné. Definuje, kde na panelu příkazů příkazy mají být umístěny.|  
|[VisibilityConstraints Element](../extensibility/visibilityconstraints-element.md)|Volitelné. Určuje, zda se statický příkazů a panely nástrojů.|  
|[Element klíčových vazeb](../extensibility/keybindings-element.md)|Volitelné. Určuje kombinace klávesových zkratek, pokud existuje, pro příkazy.|  
|[UsedCommands Element](../extensibility/usedcommands-element.md)|Volitelné. Umožňuje VSPackage volitelně implementovat svou vlastní verzi funkce původně nepodporuje jiných VSPackages.|  
|[Element symboly](http://msdn.microsoft.com/en-us/f2ddd0aa-c3dd-439e-834d-28f136a27ffa)|Volitelné. Obsahuje všechna data symbol – identifikátory GUID, ID a tak dále – pro kompilátor.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|Žádné||  
  
## <a name="see-also"></a>Viz také  
 [Visual Studio příkaz tabulky (. Soubory Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)