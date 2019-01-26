---
title: 'Průvodce: Příklad LinqToXmlDataBinding'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: aedf42e8-896c-48fa-88df-7f7c9536aa69
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 17323482bfd300dc226ae21354a3dd11bd0c1753
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55011020"
---
# <a name="walkthrough-linqtoxmldatabinding-example"></a>Průvodce: Příklad LinqToXmlDataBinding
Tento návod popisuje příklad LinqToXmlDataBinding a vysvětluje některé zajímavější obsah dva primární zdrojové soubory, *L2DBForm.xaml* a *L2DBForm.xaml.cs*.

## <a name="prerequisites"></a>Požadavky
 Předtím, než se pustíte do čtení tohoto návodu, důrazně doporučujeme sestavit a spustit LinqToXmlDataBinding program, jak je popsáno v [jak: Sestavení a spuštění příkladu linqtoxmldatabinding](../designers/how-to-build-and-run-the-linqtoxmldatabinding-example.md).

## <a name="remarks"></a>Poznámky
 LinqToXmlDataBinding program je aplikace Windows Presentation Foundation (WPF), který se skládá C# a XAML zdrojové soubory. Obsahuje vložený dokument XML, který definuje seznam knihy a umožňuje uživatelům zobrazit, přidat, odstranit a upravit tyto položky. Se skládá z následujících dvou primární zdrojové soubory:

- *L2DBForm.XAML* obsahuje kód XAML deklarace pro uživatelské rozhraní (UI) hlavního okna. Obsahuje také oddíl prostředků okna, která definuje data provider a vloženého dokumentu XML pro výpisy knihy.

- *L2DBForm.XAML.cs* obsahuje inicializační a metody zpracování událostí, které jsou přidružené uživatelské rozhraní.

  Hlavní okno je rozdělen do následujících čtyř svislé částí uživatelského rozhraní:

- **XML** zobrazí nezpracovaný zdroj dat XML vložené adresáře seznamu.

- **Rezervuje seznamu** zobrazuje jako standardní text položky adresáře a umožňuje uživateli vybrat a odstranit jednotlivé položky.

- **Upravit vybrané knihy** umožňuje uživateli upravit hodnoty přidružené k položce vybrané knihy.

- **Přidat nový adresář** umožňuje vytvořit novou položku seznamu na základě hodnot zadaných uživatelem.

## <a name="in-this-section"></a>V tomto oddílu

|Téma|Popis|
|-----------|-----------------|
|[Zdrojový kód L2DBForm.xaml](../designers/l2dbform-xaml-source-code.md)|Obsahuje obsah a popis kódu XAML v souboru L2DBForm.xaml.|
|[Zdrojový kód L2DBForm.xaml.cs](../designers/l2dbform-xaml-cs-source-code.md)|Obsahuje obsah a popis zdrojový kód C# v souboru L2DBForm.xaml.cs.|

## <a name="see-also"></a>Viz také:

- [Datové vazby WPF pomocí LINQ na ukázkový kód XML](../designers/wpf-data-binding-using-linq-to-xml-example.md)
- [Postupy: Sestavení a spuštění příkladu linqtoxmldatabinding](../designers/how-to-build-and-run-the-linqtoxmldatabinding-example.md)