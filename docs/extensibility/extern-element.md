---
title: Extern – Element | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- Extern
helpviewer_keywords:
- VSCT XML schema elements, Extern
- Extern element (VSCT XML schema)
ms.assetid: db6c3ddd-a1ba-450a-897a-bb568a5377fc
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 34e38618a153aa74bdc2449895272fc9e399c82d
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66342803"
---
# <a name="extern-element"></a>Extern – element
Extern element odkazuje libovolné externích záhlaví ( *.h*) soubory sloučit s *.vsct* soubor v době kompilace. Soubory, které chcete sloučit, musí být na cesty zahrnutí zadaný pro kompilátor VSCT nebo odkazuje [zahrnutý element](../extensibility/include-element.md). Soubory mohou být buď *.vsct* soubory nebo soubory hlaviček jazyka C++.

 Definice v souborech hlaviček musí být ve formátu "#define [Symbol] [hodnota]" hodnota může být další symbol, pokud je již definován. Podmíněné příkazy příkaz položek lze definice. Jakýkoli symbol doopravdy nepoužije se zahodí.

 Extern – Element commandtable – Element

## <a name="syntax"></a>Syntaxe

```xml
<Extern href="stdidcmd.h" />
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.

### <a name="attributes"></a>Atributy

|Atribut|Popis|
|---------------|-----------------|
|href|Povinný parametr. Cesta k souboru hlaviček:<br /><br /> href="stdidcmd.h"|
|Podmínka|Volitelné. Zobrazit [podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md).|
|jazyk|Volitelné. Výchozí jazyk všech [ \<řetězce >](../extensibility/strings-element.md) elementy v tabulce příkazu:<br /><br /> jazyk = "en-us"|

### <a name="child-elements"></a>Podřízené prvky

|Prvek|Popis|
|-------------|-----------------|
|Žádné|Žádné|

### <a name="parent-elements"></a>Nadřazené prvky

|Prvek|Popis|
|-------------|-----------------|
|[Commandtable – element](../extensibility/commandtable-element.md)|Definuje všechny prvky, které představují příkazy – to znamená, položek nabídky, nabídky, panely nástrojů a pole se seznamem – poskytující VSPackage rozhraní IDE.|

## <a name="example"></a>Příklad

```xml
<?xml version="1.0" encoding="utf-8"?>
<CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-
  18/CommandTable" xmlns:xs="http://www.w3.org/2001/XMLSchema">
    <Extern href="C:\VSCore\vscommon\inc\vsshlids.h"/>
    ...
  <Commands package="guidMyPackage">
</CommandTable>
```

## <a name="see-also"></a>Viz také:
- [Soubory tabulky (.vsct) příkaz pro Visual Studio](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
- [Jak balíčky VSPackages přidávají prvky uživatelského rozhraní](../extensibility/internals/how-vspackages-add-user-interface-elements.md)
- [Příkazy, nabídky a panely nástrojů](../extensibility/internals/commands-menus-and-toolbars.md)