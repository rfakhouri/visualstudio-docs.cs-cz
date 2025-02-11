---
title: Aspekty zabezpečení při práci s daty XML
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: fce2b708-1aef-454f-be59-52b76f359351
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5fe4ec69f879478566cce8d077bb66b34da86f3d
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68926764"
---
# <a name="security-considerations-when-working-with-xml-data"></a>Otázky zabezpečení při práci s daty XML

Toto téma popisuje problémy se zabezpečením, o kterých potřebujete znát při práci s editorem XML nebo s ladicím programem XSLT.

## <a name="xml-editor"></a>Editor XML

Editor XML je založen na textovém editoru sady Visual Studio. Spoléhá na <xref:System.Xml> třídy a a <xref:System.Xml.Xsl> zpracovává mnoho procesů XML.

- Transformace XSLT jsou spouštěny v nové doméně aplikace. Transformace XSLT jsou *v izolovaném prostoru (sandbox)* . To znamená, že se zásady zabezpečení přístupu k kódu vašeho počítače používají k určení omezených oprávnění na základě toho, kde se nachází šablona stylů XSLT. Například šablony stylů z internetového umístění mají nejvíc omezená oprávnění, zatímco šablony stylů zkopírované na pevný disk běží s úplným vztahem důvěryhodnosti.

- <xref:System.Xml.Xsl.XslCompiledTransform> Třída se používá ke kompilaci XSLT do Microsoft Intermediate Language pro rychlejší výkon během provádění.

- Schémata, která odkazují na externí umístění v souboru katalogu, se stáhnou automaticky při prvním načtení editoru XML. <xref:System.Xml.Schema.XmlSchemaSet> Třída se používá ke kompilaci schémat. Soubor katalogu, který je dodáván s editorem XML, nemá odkazy na žádná externí schémata. Uživatel musí explicitně přidat odkaz na externí schéma předtím, než Editor XML stáhne soubor schématu. Stahování HTTP se dá zakázat prostřednictvím stránky **Možnosti různých nástrojů** pro editor XML.

- Editor XML používá <xref:System.Net> třídy ke stažení schémat.

## <a name="xslt-debugger"></a>Ladicí program XSLT

Ladicí program XSLT používá spravované moduly ladění a třídy sady Visual Studio z <xref:System.Xml> oboru názvů a. <xref:System.Xml.Xsl>

- Ladicí program XSLT spouští každou transformaci XSLT v doméně aplikace v izolovaném prostoru. Zásady zabezpečení přístupu k kódu vašeho počítače se používají k určení omezených oprávnění na základě toho, kde se nachází šablona stylů XSLT. Například šablony stylů z internetového umístění mají nejvíc omezená oprávnění, zatímco šablony stylů zkopírované na pevný disk běží s úplným vztahem důvěryhodnosti.

- Šablona stylů XSLT je kompilována pomocí <xref:System.Xml.Xsl.XslCompiledTransform> třídy.

- Filtr výrazu XSLT je načten spravovaným ladicím modulem. Spravovaný modul ladění předpokládá, že veškerý kód je spuštěn z místního počítače uživatele. <xref:System.Xml.Xsl.XslCompiledTransform> Třída proto stáhne soubor XSLT do místního počítače uživatele. Je možné, že dojde k omezení zvýšení oprávnění v privilegovaném provádění všech transformací XSLT v nové doméně aplikace s omezenými oprávněními.

## <a name="see-also"></a>Viz také:

- [Aplikační domény](/dotnet/framework/app-domains/application-domains)