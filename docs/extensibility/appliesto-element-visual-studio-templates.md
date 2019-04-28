---
title: AppliesTo – Element (šablony sady Visual Studio) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
ms.assetid: 8fb1334b-d78c-405f-98b4-786e9f6b58d7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f14924ac9464cc6239564f775a122551a9d94c15
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62843642"
---
# <a name="appliesto-element-visual-studio-templates"></a>AppliesTo – element (šablony sady Visual Studio)

Určuje volitelný výraz, který odpovídá jedné nebo více možnostem (viz <xref:Microsoft.VisualStudio.Shell.Interop.VsProjectCapabilityExpressionMatcher>). Možnosti jsou vystavené typy projektů hierarchie jako vlastnost [__VSHPROPID5. VSHPROPID_ProjectCapabilities](<xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID5.VSHPROPID_ProjectCapabilities>). Tímto způsobem může šablony sdílet více typů projektů, které mají společné příslušné schopnosti.

Tento element je volitelný. Soubor šablony může obsahovat maximálně jednu jeho instanci. Tento element pouze umožňuje určit, kterou šablonu položky lze případně použít, na základě schopností aktuálně vybraného aktivního projektu. Neumožňuje určit, že šablonu položky nelze použít. Pokud `AppliesTo` chybí nebo výraz nevyjadřovat výslovný úspěšně, potom `TemplateID` nebo `TemplateGroupID` umožňuje zajistit, že šablona použitelný, jako v předchozích verzích produktu.

Zavedena v aplikaci Visual Studio 2013 Update 2. Tak, aby odkazovaly na správné verzi, najdete v článku [odkazování na sestavení doručit v aktualizaci 2 pro Visual Studio 2013 SDK](/previous-versions/dn632168(v=vs.120)).

```xml
<VSTemplate>
   <TemplateData>
      <AppliesTo>
```

## <a name="syntax"></a>Syntaxe

```xml
<AppliesTo>Capability1</AppliesTo>
```

## <a name="attributes-and-elements"></a>Atributy a elementy

Následující části popisují atributy, podřízené prvky a nadřazené prvky.

### <a name="attributes"></a>Atributy

Žádné

### <a name="child-elements"></a>Podřízené prvky

Žádné

### <a name="parent-elements"></a>Nadřazené prvky

|Prvek|Popis|
|-------------|-----------------|
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Určuje kategorii šablony.|

## <a name="text-value"></a>Textová hodnota

Je vyžadována textová hodnota. Tento text určuje schopnosti projektu.

Platná syntaxe výrazu je definována takto:

- Výraz schopnosti, například "(VisualC &#124; CSharp) + (MSTest &#124; NUnit)".

- "&#124;" Je operátor OR.

- "&" A "+" znaky jsou oba operátory.

- Znak "!" je operátor NOT.

- Závorky určují pořadí vyhodnocování.

- Hodnota null nebo prázdný výraz jsou vyhodnoceny jako shoda.

- Schopnosti projektu mohou používat libovolné znaky kromě těchto vyhrazených znaků: "'' :;,+-*/\\! ~&#124;& %$@^() ={}<> []? \t\b\n\r

## <a name="example"></a>Příklad

Následující příklad ukazuje tři různé šablony. `Template1` vztahuje na všechny typy projektů jazyka C# nebo jakýkoli jiný typ projektu, který podporuje `WindowsAppContainer` funkce. `Template2` platí pro všechny projekty jazyka C# jakéhokoli druhu. `Template3` platí pro projekty jazyka C#, které nejsou `WindowsAppContainer` projekty.

```xml
<!--  Template 1 -->
<?xml version="1.0" encoding="utf-8"?>
<VSTemplate Version="3.0.0" Type="Item" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <AppliesTo>CSharp | WindowsAppContainer</AppliesTo>
    </TemplateData>
</VSTemplate>

<!--  Template 2 -->
<?xml version="1.0" encoding="utf-8"?>
<VSTemplate Version="3.0.0" Type="Item" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <AppliesTo>CSharp</AppliesTo>
    </TemplateData>
</VSTemplate>

<!--  Template 1 -->
<?xml version="1.0" encoding="utf-8"?>
<VSTemplate Version="3.0.0" Type="Item" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <AppliesTo>CSharp_Class + (!WindowsAppContainer)</AppliesTo>
    </TemplateData>
</VSTemplate>
```

## <a name="see-also"></a>Viz také:

- [Visual Studio odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md)
- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)