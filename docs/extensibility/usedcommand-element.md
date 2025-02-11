---
title: Usedcommand – Element | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- UsedCommands element (VSCT XML schema)
- VSCT XML schema elements, UsedCommands
ms.assetid: 99cd05d3-644a-42ff-b289-8458cd1b20c0
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 36dbfa484b69832c67c7a1dd28f217706e1a91a6
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66316307"
---
# <a name="usedcommand-element"></a>UsedCommand – element
Umožňuje pro přístup k příkazu, který je definován v jiném souboru .vsct VSPackage. Například, pokud vaše VSPackage používá standardní **kopírování** příkaz, který je definovaný [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] prostředí, můžete přidat příkaz nabídky nebo panelu nástrojů bez znova implementovány.

## <a name="syntax"></a>Syntaxe

```
<UsedCommand guid="guidMyCommandGroup" id="MyCommand" />
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.

### <a name="attributes"></a>Atributy

|Atribut|Popis|
|---------------|-----------------|
|identifikátor GUID|Povinný parametr. Identifikátor GUID, které odpovídá páru ID identifikátoru GUID identifikující příkazu.|
|id|Povinný parametr. ID, které odpovídá páru ID identifikátoru GUID identifikující příkazu.|
|Podmínka|Volitelné. Zobrazit [podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md).|

### <a name="child-elements"></a>Podřízené elementy

|Prvek|Popis|
|-------------|-----------------|
|Žádný||

### <a name="parent-elements"></a>Nadřazené elementy

|Prvek|Popis|
|-------------|-----------------|
|[UsedCommands – element](../extensibility/usedcommands-element.md)|Seskupí usedcommand – elementy a ostatní usedcommands – seskupení.|

## <a name="remarks"></a>Poznámky
 Přidáním příkazu, který bude `<UsedCommands>` informuje VSPackage elementu, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] prostředí, že sady VSPackage vyžaduje, aby příkaz. Měli byste přidat `<UsedCommand>` – element pro kterýkoli příkaz vašeho balíčku vyžaduje, aby nemusí obsahovat všechny verze a konfigurace sady Visual Studio. Například pokud váš balíček volá příkaz, který je specifický pro aplikaci Visual C++, příkaz nebude dostupné uživatelům aplikace Visual Web Developer nezahrnete `<UsedCommand>` – element pro příkaz.

## <a name="example"></a>Příklad

```
<UsedCommands>
  <UsedCommand guid="guidVSStd97" id="cmdidCut"/>
  <UsedCommand guid="guidVSStd97" id="cmdidCopy"/>
  <UsedCommand guid="guidVSStd97" id="cmdidPaste"/>
</UsedCommands>
```

## <a name="see-also"></a>Viz také
- [UsedCommands – element](../extensibility/usedcommands-element.md)
- [Soubory tabulek příkazů sady Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)