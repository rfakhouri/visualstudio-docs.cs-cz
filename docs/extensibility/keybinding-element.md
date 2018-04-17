---
title: KeyBinding Element | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT XML schema elements, KeyBindings
- KeyBinding element (VSCT XML schema)
ms.assetid: e55a1098-15df-42a9-9f87-e3a99cf437dd
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 226a5913cbaa151689a886dc88986f7de8cc29f6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="keybinding-element"></a>KeyBinding Element
KeyBinding element určuje klávesové zkratky pro příkazy.  
  
 Příkazy může mít jeden a duální vazeb klíče s nimi spojených. CTRL + S pro je například jednu vazbu klíče **Uložit** příkaz. Duální vazeb klíče vyžadují dvě po sobě jdoucích kombinace kláves pro spuštění příkazu. Příklad duální vazby klíče je CTRL + K, CTRL + K nastavení záložky.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<Keybinding guid="MyGuid" id="MyId" Editor="MyEditor" key1="B" key2="x" mod1="Control" mod2="Alt" />  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|Identifikátor GUID|Požadováno.|  
|id|Požadováno.|  
|editor|Požadováno. Editor GUID označuje kontext úpravy, pro kterou bude klávesová zkratka aktivní. Hodnota oboru globální vazba je "guidVSStd97".|  
|key1|Požadováno. Platné hodnoty patří všechny typable alfanumerických znaků a také letopočty šestnáctkové hodnoty 0 x před sebou a [VK_constants](https://msdn.microsoft.com/en-us/library/windows/desktop/dd375731.aspx).|  
|mod1|Volitelné. Libovolnou kombinaci kláves CTRL, ALT a SHIFT oddělte mezerou.|  
|key2|Volitelné. Platné hodnoty patří všechny typable alfanumerických znaků a také letopočty šestnáctkové hodnoty 0 x před sebou a [VK_constants](https://msdn.microsoft.com/en-us/library/windows/desktop/dd375731.aspx).|  
|mod2|Volitelné. Libovolnou kombinaci kláves CTRL, ALT a SHIFT oddělte mezerou.|  
|emulátor|Volitelné.|  
|Podmínka|Volitelné. V tématu [podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|Nadřazené||  
|Poznámka||  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[KeyBindings – element](../extensibility/keybindings-element.md)|Elementy KeyBinding skupin a dalších klíčových vazeb seskupení.|  
  
## <a name="example"></a>Příklad  
  
```  
<KeyBindings>  
  <KeyBinding guid="guidWidgetPackage" id="cmdidUpdateWidget"   
    editor="guidWidgetEditor" key1="VK_F5"/>  
  <KeyBinding guid="guidWidgetPackage" id="cmdidRunWidget"   
    editor="guidWidgetEditor" key1="VK_F5" mod1="Control"/>  
</KeyBindings>  
```  
  
## <a name="see-also"></a>Viz také  
 [Element klíčových vazeb](../extensibility/keybindings-element.md)   
 [Soubory tabulek příkazů sady Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
