---
title: Ochrana dokumentů v řešeních na úrovni dokumentu
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- restricted permissions [Office development in Visual Studio]
- permissions [Office development in Visual Studio]
- workbooks [Office development in Visual Studio], restricted permissions
- Office documents [Office development in Visual Studio], restricted permissions
- documents [Office development in Visual Studio], restricted permissions
author: John-Hart
ms.author: johnhart
manager: douge
ms.workload:
- office
ms.openlocfilehash: b6894aa05adf55945383cb3c2e28b8c5fdebdc16
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53908850"
---
# <a name="document-protection-in-document-level-solutions"></a>Ochrana dokumentů v řešeních na úrovni dokumentu
  Můžete využívat funkce ochrany aplikace Microsoft Office Word a Microsoft Office Excel v projektech na úrovni dokumentu. Tyto funkce blokuje neoprávněné uživatele provádět změny chráněné části dokumentu.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Pomocí aplikace Excel, můžete zapnout ochranu zapnout a vypnout sešit je v Návrháři otevřený. Použití aplikace Word, můžete zapnout ochranu pouze mimo návrháře. Za běhu můžete povolit nebo zakázat ochranu prostřednictvím kódu programu pro aplikace Word a Excel.  
  
 Když na dokument, který je otevřen v Návrháři je povolená ochrana dokumentů, odeberou se všechny ovládací prvky z **nástrojů** nebo jsou k dispozici, a nelze přetáhnout nic z **zdroje dat** okno dokumentu.  
  
## <a name="serverdocument-and-protected-documents"></a>ServerDocument a chráněné dokumenty  
 Pokud je dokument chráněný, přístupné z mezipaměti dat mimo dokumentu. Nelze použít <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> třídy načíst nebo manipulaci s daty, která se uloží do mezipaměti v chráněný dokument, nebo použít jiné metody <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ServerDocument> třídy.  
  
## <a name="word-document-protection-in-the-designer"></a>Ochrana dokumentů aplikace Word v Návrháři  
 Pokud chcete přidat ochranu Wordového dokumentu nebo šablony je otevřen v sadě Visual Studio, nelze spustit, vynucovat ochranu v návrháři. Dokument je v režimu návrhu, zatímco je otevřen v sadě Visual Studio a musí se v spustit režim předtím, než můžete začít vynucovat ochranu.  
  
 Pokud vytvoříte projekt, který používá existující dokument aplikace Word, který má zapnutou ochranu, je dokument chráněný při otevření v návrháři. Nelze upravit chráněné části dokumentu, ale můžete pořád napsat kód v editoru kódu pro automatizaci dokumentu. Také nelze sestavení projektu je-li povolit ochranu, když je dokument otevřen v sadě Visual Studio.  
  
 Můžete vypnout ochranu dokumentu je v Návrháři otevřený, aby mohli dokument upravovat a sestavte projekt. Ochranu pro kopírování v Návrháři nelze vypnout, při ladění; dokument, který se otevře při ladění je samostatná kopie z jedné otevřít v Návrháři (výstup kopie je uložena v *\bin* adresáře v jazyce Visual Basic a *\bin\debug* adresáře pro C# ).  
  
 Můžete povolit ochranu na kopii dokumentu, který se otevře v Návrháři zavírání projektu v sadě Visual Studio, otevřením kopii dokumentu, který je v adresáři projektu a zapnutí ochrany.  
  
## <a name="enforce-word-document-protection-on-build"></a>Vynutit ochrana dokumentů aplikace Word v sestavení  
 Spustí aplikace Visual Studio použít zámek pro šablony Wordových dokumentů a během procesu sestavení tak, aby se po otevření dokumentu pro ladění povolit ochranu. Dokument je chráněný pomocí prázdné heslo.  
  
 Ochrana je povoleno během sestavení tak, pokud není kód v dokumentu <xref:Microsoft.Office.Tools.Word.Document.Startup> událostí, který může způsobit, že výjimky nebo změnit chování aplikace, tento kód může být ladění správně. Pokud povolíte ochranu po otevření dokumentu, inicializační kód nelze ladit, nebo testovat.  
  
## <a name="setting-the-password"></a>Nastavení hesla  
 Visual Studio automaticky povolí ochranu, ale ve výchozím nastavení poskytuje žádné heslo. Pokud chcete ochranu dokumentů heslo, musíte jej přidat před nasazení vašeho řešení. Přidání hesla umožňuje autorizovaným uživatelům odebrat ochranu z dokumentu. bez hesla nelze snadno odebrat ochranu. Podrobnosti o nastavení hesla najdete v nápovědě v konkrétní aplikaci Office.  
  
## <a name="see-also"></a>Viz také:  
 [Postupy: Zamykání dokumentů a částí dokumentů](../vsto/how-to-programmatically-protect-documents-and-parts-of-documents.md)   
 [Ukázky vývoje pro Office a názorné postupy](../vsto/office-development-samples-and-walkthroughs.md)   
 [Přehled rozšíření spravovaného kódu a správy přístupových práv](../vsto/information-rights-management-and-managed-code-extensions-overview.md)   
 [Ochrana dokumentů Office heslem](../vsto/password-protection-on-office-documents.md)   
 [Postupy: Povolit kód ke spuštění pozadí dokumentů s omezenými oprávněními](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md)   
 [Návrh a vytvoření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)  
