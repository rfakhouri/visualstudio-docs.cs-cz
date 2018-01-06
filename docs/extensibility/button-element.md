---
title: "Tlačítko Element | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Buttons element (VSCT XML schema)
- VSCT XML schema elements, Buttons
ms.assetid: 96dccf51-2b00-4700-9d28-924b34c21ecd
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 5af5dce3edf1ac2910af5f8d593ed8e316cff721
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="button-element"></a>Button Element
Definuje element, který může uživatel zasahovat. Tlačítka můžou být různé typy: tlačítko, tlačítko nabídky a SplitDropDown.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<Button guid="guidMyCommandSet" id="MyCommand" priority="0x102" type="button">  
  <Parent>... </Parent>  
  <Icon>... </Icon>  
  <CommandFlag>... </CommandFlag>  
  <Strings>... </Strings>  
</Button>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|Identifikátor GUID|Požadováno. Identifikátor GUID identifikátor GUID nebo ID příkazu.|  
|id|Požadováno. ID identifikátor GUID nebo ID příkazu.|  
|Priorita|Volitelné. Číselnou hodnotu, která určuje prioritu.|  
|– typ|Volitelné. Výčtová hodnota, která určuje druh tlačítko.<br /><br /> Pokud není zadaný, použije tlačítko.<br /><br /> Tlačítko<br /> Standardní příkaz, který se zobrazí na panely nástrojů (obvykle jako ikony tlačítka), nabídky a kontextové nabídky.<br /><br /> Tlačítko nabídky<br /> Položky nabídky, která není provedení příkazu, ale vytváří jiné nabídky.<br /><br /> SplitDropDown<br /> Ovládací prvky, jako jsou tlačítka Zpět a znovu na standardním panelu nástrojů v aplikaci Microsoft Word.|  
|Podmínka|Volitelné. V tématu [podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Parent – element](../extensibility/parent-element.md)|Volitelné. Nadřazený element tlačítko.|  
|[Icon – element](../extensibility/icon-element.md)|Volitelné. Ikony přidružené tlačítko.|  
|[Command Flag – element](../extensibility/command-flag-element.md)|Požadováno. Platné hodnoty CommandFlag pro tlačítko jsou následujícím způsobem.<br /><br /> -AllowParams<br /><br /> -CommandWellOnly<br /><br /> -DefaultDisabled<br /><br /> -DefaultInvisible<br /><br /> -DontCache<br /><br /> -DynamicItemStart<br /><br /> -DynamicVisibility<br /><br /> -FixMenuController<br /><br /> -IconAndText<br /><br /> -NoButtonCustomize<br /><br /> -NoCustomize<br /><br /> -NoKeyCustomize<br /><br /> -NoShowOnMenuController<br /><br /> -Pict<br /><br /> -PostExec<br /><br /> -ProfferedCmd<br /><br /> -RouteToDocs<br /><br /> -TextCascadeUseBtn<br /><br /> -TextMenuUseButton<br /><br /> -TextChanges<br /><br /> -TextChangesButton<br /><br /> -TextContextUseButton<br /><br /> -TextMenuCtrlUseMenu<br /><br /> -TextMenuUseButton<br /><br /> -Typu TextOnly|  
|[Strings – element](../extensibility/strings-element.md)|Požadováno. Podřízená [ButtonText Element](../extensibility/buttontext-element.md) musí být definován.|  
|Poznámka|Volitelný komentář.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Buttons – element](../extensibility/buttons-element.md)|Tlačítko prvky skupiny.|  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu definuje v souboru .vsct tlačítko.  

 ```xml
<Button guid="guidMenuTextCmdSet" id="cmdidMyCommand" priority="0x0100" type="Button">
    <Parent guid="guidMenuTextCmdSet" id="MyMenuGroup" />
    <Icon guid="guidImages" id="bmpPic1" />
    <CommandFlag>TextChanges</CommandFlag>
    <Strings>
          <CommandName>cmdidMyCommand</CommandName>
          <ButtonText>My Command name</ButtonText>
    </Strings>
</Button>
 ```
 
## <a name="see-also"></a>Viz také  
 [Soubory tabulek příkazů sady Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)