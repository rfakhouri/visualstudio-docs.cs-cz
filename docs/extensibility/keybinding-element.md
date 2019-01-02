---
title: Keybinding – Element | Dokumentace Microsoftu
ms.date: 11/04/2016
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
ms.openlocfilehash: 6c401b1f5179fa03dbd43ffbcff3bd2f0151340c
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53931669"
---
# <a name="keybinding-element"></a>Keybinding – element
Keybinding – element určuje klávesové zkratky pro příkazy.  
  
 Příkazy může mít jeden a duální klávesové zkratky, které jsou k nim má přiřazené. Příkladem jednoho vazbu klíče je **Ctrl**+**S** pro **Uložit** příkazu. Duální klávesové zkratky vyžadují dvě po sobě jdoucích kombinace kláves pro spuštění příkazu. Je například duální vazbu klíče <strong>Ctrl*+</strong>K<strong>,</strong>Ctrl<strong>+</strong>K** nastavit záložky.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<Keybinding guid="MyGuid" id="MyId" Editor="MyEditor" key1="B" key2="x" mod1="Control" mod2="Alt" />  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|identifikátor GUID|Povinný parametr.|  
|id|Povinný parametr.|  
|editor|Povinný parametr. Identifikátor GUID editoru určuje kontext úprav, pro kterou bude klávesová zkratka aktivní. Hodnota oboru globální vazby je "guidVSStd97".|  
|key1|Povinný parametr. Platné hodnoty jsou všechny typable alfanumerické znaky a dvěma číslicemi šestnáctkových hodnot předchází 0 x a [VK_constants](/windows/desktop/inputdev/virtual-key-codes).|  
|mod1|Volitelné. Libovolnou kombinaci **Ctrl**, **Alt**, a **Shift** odděleny mezerou.|  
|key2|Volitelné. Platné hodnoty jsou všechny typable alfanumerické znaky a dvěma číslicemi šestnáctkových hodnot předchází 0 x a [VK_constants](/windows/desktop/inputdev/virtual-key-codes).|  
|mod2|Volitelné. Libovolnou kombinaci **Ctrl**, **Alt**, a **Shift** odděleny mezerou.|  
|Emulátor|Volitelné.|  
|Podmínka|Volitelné. Zobrazit [podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Podřízené prvky  
  
|Prvek|Popis|  
|-------------|-----------------|  
|Nadřazené||  
|Poznámka||  
  
### <a name="parent-elements"></a>Nadřazené prvky  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Keybindings – element](../extensibility/keybindings-element.md)|Seskupí elementy klávesové zkratky a další seskupení klávesové zkratky.|  
  
## <a name="example"></a>Příklad  
  
```  
<KeyBindings>  
  <KeyBinding guid="guidWidgetPackage" id="cmdidUpdateWidget"   
    editor="guidWidgetEditor" key1="VK_F5"/>  
  <KeyBinding guid="guidWidgetPackage" id="cmdidRunWidget"   
    editor="guidWidgetEditor" key1="VK_F5" mod1="Control"/>  
</KeyBindings>  
```  
  
## <a name="see-also"></a>Viz také:  
 [Keybindings – element](../extensibility/keybindings-element.md)   
 [Soubory tabulky (.vsct) příkaz pro Visual Studio](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
