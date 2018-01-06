---
title: "Ochrana v řešeních na úrovni dokumentu dokumentu | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- restricted permissions [Office development in Visual Studio]
- permissions [Office development in Visual Studio]
- workbooks [Office development in Visual Studio], restricted permissions
- Office documents [Office development in Visual Studio], restricted permissions
- documents [Office development in Visual Studio], restricted permissions
ms.assetid: a25472ad-03f0-4804-9d19-e5ff71340d49
caps.latest.revision: "36"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: cb0ccb9369c3430cf04e7e7c6b62335721e8005f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="document-protection-in-document-level-solutions"></a>Ochrana dokumentů v řešeních na úrovni dokumentu
  Můžete využívat funkce ochrany aplikace Microsoft Office Word a Microsoft Office Excel v projekty na úrovni dokumentu. Tyto funkce brání neoprávněným uživatelům v provádění změn chráněných části dokumentu.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Pomocí aplikace Excel, můžete zapnout ochranu zapnout a vypnout sešit je otevřen v návrháři. Použití aplikace Word, můžete zapnout ochranu pouze mimo designer. V době běhu můžete povolit nebo zakázat ochranu prostřednictvím kódu programu pro Word a Excel.  
  
 Pokud je ochrana dokumentu v dokumentu, který je otevřít v Návrháři povoleno, všechny ovládací prvky jsou odebrány z **sada nástrojů** nebo nebudou k dispozici, a nelze přetáhnout nic z **zdroje dat** okna dokumentu.  
  
## <a name="serverdocument-and-protected-documents"></a>ServerDocument a chráněné dokumenty  
 Pokud je dokument chráněný, datové mezipaměti není přístupná z mimo dokumentu. Nelze použít <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> třídy načíst nebo pracovat s daty, která se uloží do mezipaměti v chráněný dokument, nebo pomocí jiných metod <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ServerDocument> třídy.  
  
## <a name="word-document-protection-in-the-designer"></a>Ochrana dokumentů aplikace Word v Návrháři  
 Pokud přidáte ochrany na dokument aplikace Word nebo šablonu je otevřen v sadě Visual Studio, nelze spustit, vynucovat ochranu v návrháři. Dokument je v režimu návrhu, když je otevřen v sadě Visual Studio, a musí být v spuštěn režimu předtím, než můžete začít vynucovat ochranu.  
  
 Pokud vytvoříte projekt, který používá stávající dokument aplikace Word, který má zapnutou ochranu, je dokument chráněný otevřené v návrháři. Nelze upravit části chráněného dokumentu, ale můžete pořád psaní kódu v editoru kódu k automatizaci dokumentu. Můžete také nemůže vytvořit projekt Pokud je povolena ochrana dokumentu je otevřen v sadě Visual Studio.  
  
 Můžete vypnout ochranu dokumentu je otevřen v návrháři, aby mohli dokument upravovat a sestavte projekt. Ochranu pro kopírování v Návrháři nelze vypnout, při ladění; dokument, který otevře během ladění je samostatná kopie z jedné otevřít v Návrháři (výstup kopie je uložena v adresáři \bin jazyka Visual Basic a \bin\debug adresář pro jazyk C#).  
  
 Můžete povolit ochranu na kopii dokumentu, které se otevře v Návrháři zavřít projekt v sadě Visual Studio, otevřením kopii dokumentu, který je v adresáři projektu a zapnutí ochrany.  
  
## <a name="enforcing-word-document-protection-on-build"></a>Vynucení ochrana dokumentů aplikace Word na sestavení  
 Visual Studio spustí, vynucovat ochranu dokumentů aplikace Word a šablony během procesu sestavení tak, aby po otevření dokumentu pro ladění zapnutá ochrana. Je dokument chráněný pomocí prázdné heslo.  
  
 Ochrana je povolena při sestavování proto, pokud je kód v dokumentu <xref:Microsoft.Office.Tools.Word.Document.Startup> událost, která může způsobit, že výjimky nebo změnit chování aplikace, tento kód může být vyladěnou správně. Pokud povolíte ochranu po otevření dokumentu, inicializace kód nelze ladit nebo testována.  
  
## <a name="setting-the-password"></a>Nastavení hesla  
 Visual Studio automaticky povolí ochranu, ale poskytuje ve výchozím nastavení žádné heslo. Pokud chcete, aby ochrana dokumentu heslo, musíte jej přidat před nasazením řešení. Přidání hesla umožňuje autorizovaným uživatelům odebrání ochrany dokumentu. bez zadání hesla nelze snadno odebrat ochranu. Podrobnosti o nastavení hesla, najdete v tématu nápovědy v konkrétní aplikaci Office.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: zamykání dokumentů a částí dokumentů prostřednictvím kódu programu](../vsto/how-to-programmatically-protect-documents-and-parts-of-documents.md)   
 [Office Ukázky a návody vývoje](../vsto/office-development-samples-and-walkthroughs.md)   
 [Přehled rozšíření spravovaného kódu a Information Rights Management](../vsto/information-rights-management-and-managed-code-extensions-overview.md)   
 [Ochrana heslem v dokumentech Office](../vsto/password-protection-on-office-documents.md)   
 [Postupy: povolení kódu spuštění na pozadí dokumentů s omezenými oprávněními](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md)   
 [Navrhování a tvorba řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)  
  
  