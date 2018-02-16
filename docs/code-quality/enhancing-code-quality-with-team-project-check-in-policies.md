---
title: "Zlepšení kvality kódu pomocí týmového projektu vrácení se změnami zásad | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code quality, using check-in policies
- team-based development, enhancing code quality
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c82bc929fa7633719c06569cb3dded5df651a349
ms.sourcegitcommit: d6327b978661c0a745bf4b59f32d8171607803a3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/01/2018
---
# <a name="enhancing-code-quality-with-team-project-check-in-policies"></a>Zvýšení kvality kódu použitím zásad vracení se změnami týmového projektu

Pokud používáte Team Foundation verze ovládacího prvku (TFVC), můžete vytvořit zásady vrácení se změnami pro týmové projekty. k vynucení postupů které vedou k lepší kód a efektivnější vývoj skupiny. Vrácení se změnami zásad představuje pravidla, která jsou nastavené na úrovni týmového projektu a vynucuje u počítačů, developer, než se povolí kódu se změnami.

Můžete určit těchto týmového projektu vrácení se změnami zásad:

- **Sestavení**: vyžaduje se, že zalomení sestavení, které byly vytvořeny během sestavení musíte opravit dřív, než nové vrácení se změnami.

- **Komentáře změn**: vyžaduje, aby uživatelé zadali komentáře při vrácení se změnami změny.

- **Analýza kódu**: vyžaduje spuštění analýzy kódu před vrácení se změnami.

- **Pracovní položky**: vyžaduje, aby jeden nebo více pracovních položek přidružené kontrola-v.

> [!IMPORTANT]
> Používání zásad vrácení se změnami, musíte být připojeni k [!INCLUDE[vststfsLong](../code-quality/includes/vststfslong_md.md)].

## <a name="common-tasks"></a>Obecné úlohy

|Úloha|Podpůrný obsah|
|----------|------------------------|
|**Vytváření a používání zásad vrácení se změnami analýzy kódu:** můžete vybrat z standardní sadu pravidel analýzy kódu, nebo můžete vytvořit vlastní sadu.|[Vytváření a používání zásad vrácení se změnami Analýzy kódu](../code-quality/creating-and-using-code-analysis-check-in-policies.md)|

## <a name="related-tasks"></a>Související úlohy

|Úloha|Podpůrný obsah|
|----------|------------------------|
|**Pomocí analýzy kódu v procesu vývoje:** členové týmu spuštění analýzy kódu na svých počítačích vývoj. V sadě Visual Studio, vývojáři konfigurace a spuštění spuštění analýzy kódu pro kód jednotlivých projektů, zobrazit a analyzovat problémy nalezena. je spuštěn a vytváření pracovních položek pro upozornění.|[Analýza kvality aplikace](../code-quality/analyzing-application-quality-by-using-code-analysis-tools.md)|
|**Vytváření a spouštění testování částí:** testování částí poskytnout vývojáři a testerům, sada rychlý způsob, jak hledat logické chyby v metody třídy v projektu C#, Visual Basic a C++. Testování částí můžete vytvořit jednou a spustit při každém tohoto zdrojového kódu se změní na Ujistěte se, že byly zavedeny žádné chyby.|[Testování částí kódu](../test/unit-test-your-code.md)|
|**Sledování pracovních položek a závad:** pracovní položky můžete použít ke sledování a správě pracovní i informace o týmového projektu. Pracovní položka je databáze záznam, který [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)] používá ke sledování přiřazení a průběh práce. Různé typy pracovních položek můžete sledovat různé typy práce, například požadavky zákazníků, chyby produktu a vývojářských úloh.|[Pracovní položky (VSTS)](/vsts/work/work-items/index)|

## <a name="external-resources"></a>Externí zdroje

[Testování pro nastavené průběžné doručování s Visual Studio 2012 – kapitoly 2: testování částí: testování uvnitř](http://go.microsoft.com/fwlink/?LinkID=255188)