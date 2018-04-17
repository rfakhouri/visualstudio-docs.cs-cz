---
title: Element pole se seznamem | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Combos element (VSCT XML schema)
- VSCT XML schema elements, Combos
ms.assetid: 392e3063-f0a0-4130-9583-23bd2aa3fa36
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ca91102467755610144e4d24405e89ace5a013b7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="combo-element"></a>Element pole se seznamem
Definuje příkazy, které se zobrazují v pole se seznamem. Existují čtyři typy pole se seznamem, následujícím způsobem: DropDownCombo, DynamicCombo, IndexCombo a MRUCombo.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<combo guid="guidMyCommandSet" id="MyCommand" defaultWidth="20" idCommandList="MyCommandListID" priority="0x102" type="DropDownCombo">  
  <Parent>... </Parent  
  <CommandFlag>... </CommandFlag>  
  <Strings>... </Strings>  
</combo>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|Identifikátor GUID|Požadováno. Identifikátor GUID identifikátor GUID nebo ID příkazu.|  
|id|Požadováno. ID identifikátor GUID nebo ID příkazu.|  
|defaultWidth|Požadováno. Celé číslo, které určuje šířku pixelů pro pole se seznamem.|  
|idCommandList|Požadováno. ID, které se odešle cíli active příkaz načíst seznam položek, který se má zobrazit v seznamu. ID bude ve stejném oboru GUID jako ovládací prvek.|  
|Priorita|Volitelné. Číselnou hodnotu, která určuje prioritu.|  
|– typ|Volitelné. Výčtová hodnota, která určuje typ tlačítka.<br /><br /> Pokud není zadaný, použije tlačítko.<br /><br /> DropDownCombo<br /> VSPackage zodpovídá za vyplnění obsah pro toto pole se seznamem. Uživatele nelze nic zadejte do textového pole tomto rozevíracího seznamu.<br /><br /> DynamicCombo<br /> VSPackage zodpovídá za vyplnění obsah toto pole se seznamem. Uživatel můžete upravit toto pole se seznamem a také vyberte položky v něm.<br /><br /> IndexCombo<br /> Stejné jako DynamicCombo s výjimkou, že vyvolá index položky, nikoli jeho textu.<br /><br /> MRUCombo<br /> Integrované vývojové prostředí (IDE) jménem VSPackage sestavil.  Uživatele můžete upravit v tomto poli se seznamem. Prostředí IDE pamatuje až 16 poslední položky na pole se seznamem.<br /><br /> Pokud uživatel vybere něco v poli se seznamem nebo zadá něco nové, upozorní IDE odpovídající VSPackage.|  
|Podmínka|Volitelné. V tématu [podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|Nadřazené|Volitelné. Nadřazený element tlačítko.|  
|CommandFlag|Požadováno. V tématu [příkaz příznak Element](../extensibility/command-flag-element.md). Platné hodnoty CommandFlag pro tlačítko jsou následujícím způsobem.<br /><br /> -CaseSensitive<br /><br /> -CommandWellOnly<br /><br /> -DefaultDisabled<br /><br /> -DefaultInvisible<br /><br /> -DynamicVisibility<br /><br /> -Filtrování kláves<br /><br /> -IconAndText<br /><br /> -NoAutoComplete<br /><br /> -NoButtonCustomize<br /><br /> -NoCustomize<br /><br /> -NoKeyCustomize<br /><br /> -StretchHorizontally|  
|Řetězce|Požadováno. V tématu [řetězce Element](../extensibility/strings-element.md). Podřízený element ButtonText musí být definovaný.|  
|Poznámka|Volitelný komentář.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Commands – element](../extensibility/commands-element.md)|Představuje kolekci příkazů na panelu nástrojů VSPackage.|  
  
## <a name="example"></a>Příklad  
  
```  
<Combo guid="guidWidgetPackage" id="cmdidInsertOptions"  
  defaultWidth="100" idCommandList="cmdidGetInsertOptionsList">  
  <CommandFlag>DynamicVisibility</CommandFlag>  
  <Strings>  
    <ButtonText>Select Insert Options</ButtonText>  
  </Strings>  
</Combo>  
  
<Combo guid="guidWidgetPackage" id="cmdidInsertOptions"  
  priority="0x0500" type="DropDownCombo" defaultWidth="100"  
  idCommandList="cmdidGetInsertOptionsList">  
  <Parent guid="cmdSetGuidWidgetCommands" id="groupIDFileEdit">  
  <CommandFlag>DynamicVisibility</CommandFlag>  
  <Strings>  
    <ButtonText>Select Insert Options</ButtonText>  
  </Strings>  
</Combo>  
```  
  
## <a name="see-also"></a>Viz také  
 [Soubory tabulek příkazů sady Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)