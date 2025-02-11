---
title: Aspekty zabezpečení při práci s daty XML | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: fce2b708-1aef-454f-be59-52b76f359351
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 448396ebf8bf6318a22d7c6b05037d3ea43b0fd5
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65697131"
---
# <a name="security-considerations-when-working-with-xml-data"></a>Aspekty zabezpečení při práci s daty XML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Toto téma popisuje problémy se zabezpečením, které je potřeba vědět o při práci s editorem XML nebo ladicí program XSLT.  
  
## <a name="xml-editor"></a>Editor XML  
 XML Editor je založena na Visual Studio textovém editoru. Využívá <xref:System.Xml> a <xref:System.Xml.Xsl> třídy pro zpracování řadu procesů XML.  
  
- Transformace XSLT jsou provedeny v nové doméně aplikace. Transformace XSLT jsou *v izolovaném prostoru*; to znamená, zásady zabezpečení přístupu kódu v počítači se používá k určení omezená oprávnění na základě na místě, kde šablony stylů XSLT. Například listů stylu z umístění v Internetu mít nejvíce omezená oprávnění, že šablony stylů zkopírovány na váš pevný disk, spusťte s úplnou důvěryhodností.  
  
- <xref:System.Xml.Xsl.XslCompiledTransform> Třída se používá ke kompilaci XSLT pro jazyk Microsoft intermediate language pro dosažení vyššího výkonu během provádění.  
  
- Schémata, které odkazují na externím místě v souboru katalogu staženy automaticky při prvním načtení editoru XML. <xref:System.Xml.Schema.XmlSchemaSet> Třída se používá ke kompilaci schémata. Soubor katalogu, který se dodává s editorem XML neobsahuje odkazy na všechny externí schémata. Uživatel musí explicitně přidat odkaz na externí schéma před editoru XML, soubory ke stažení souboru schématu. Stahuje se protokol HTTP se dají zakázat pomocí **různé možnosti nástrojů** stránky pro Editor XML.  
  
- XML Editor používá <xref:System.Net> třídy ke stažení schémata  
  
## <a name="xslt-debugger"></a>Ladicí program XSLT  
 Ladicí program XSLT využívá spravovaného ladicího stroje sady Visual Studio a tříd z <xref:System.Xml> a <xref:System.Xml.Xsl> oboru názvů.  
  
- Ladicí program XSLT spouští každá transformace XSLT v doméně aplikace v izolovaném prostoru. Zásady zabezpečení přístupu kódu v počítači se používá k určení omezená oprávnění na základě na místě, kde šablony stylů XSLT. Například listů stylu z umístění v Internetu mít nejvíce omezená oprávnění, že šablony stylů zkopírovány na váš pevný disk, spusťte s úplnou důvěryhodností.  
  
- Šablony stylů XSLT je zkompilován pomocí <xref:System.Xml.Xsl.XslCompiledTransform> třídy.  
  
- Chyba při vyhodnocování výrazu XSLT je načtena pomocí spravovaného ladicího stroje. Spravovaného ladicího stroje se předpokládá, že všechny kód se spouští z místního počítače uživatele. Odpovídajícím způsobem <xref:System.Xml.Xsl.XslCompiledTransform> třídy stáhne soubor XSLT do místního počítače uživatele. Možnost, že mohlo dojít ke zvýšení úrovně oprávnění v provádění oprávnění zmírnit provádění všechny transformace XSLT v nové doméně aplikace s omezenými oprávněními  
  
## <a name="see-also"></a>Viz také  
 [Aplikační domény](https://msdn.microsoft.com/39e57d07-a740-4cd4-ae82-e119ea3856c1)
