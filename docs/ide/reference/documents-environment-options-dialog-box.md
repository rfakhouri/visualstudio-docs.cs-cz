---
title: "Dokumenty, prostředí, dialogové okno Možnosti | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.Environment.Documents
- VS.ToolsOptionsPages.Environment.Documents
- VS.ToolsOptionsPag.Environment.Documents
helpviewer_keywords:
- Documents Environment Options dialog box
- defaults, directories
- error messages, customizing
- files [Visual Studio], default options
- files [Visual Basic], auto-loading modified
- windows, customizing environment
- in-memory editing
- folders [Visual Studio], specifying where Open File goes
- Open File dialog box
- windows, enabling re-use of current
- notifications, files changed
- files [Visual Studio], displaying in Solution Explorer
- default directories
- read-only files, editing
- Options dialog box, showing Miscellaneous Files
- directories [Visual Studio], IDE environment options
- Options dialog box, Documents page
- warnings, files changed
- Solution Explorer, displaying files in
ms.assetid: 4e3ccf1b-cd68-4db6-9470-710c911b47fc
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c7d9f7cef6c0dfa35a4a718c0918fbc55409af04
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="documents-environment-options-dialog-box"></a>Dokumenty, prostředí, dialogové okno Možnosti
Pomocí této stránky **možnosti** dialogové okno pro řízení zobrazení dokumentů v integrované vývojové prostředí (IDE) a spravovat externí změny dokumentů a souborů. Tohoto dialogového okna můžete přejít pomocí kliknutím na tlačítko **možnosti** na **nástroje** nabídce a potom vyberete **dokumenty** v **prostředí** uzlu. Pokud **dokumenty** nejsou uvedené v seznamu vyberte **zobrazit všechna nastavení** v **možnosti** dialogové okno.  
  
> [!NOTE]
>  K dispozici v dialogových oken, názvy a umístění příkazy nabídky, které vidíte, se může lišit od co je popsáno v nápovědě v závislosti na aktivním nastavení nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md).  
  
 **Pokud uloženy opakovaně používat aktuální okna dokumentu.**  
 Pokud vybraná, zavře dokumentu, pokud byla uložena a nový dokument se otevře v rámci stejného časového období. Pokud vaše aktuální dokument nebyl uložen, zůstane otevřený a nový dokument se otevře v samostatném okně. Pokud tato možnost vybrána, otevřete nové dokumenty vždy v samostatném systému windows.  
  
 Je-li provést několika dokumentů vyjmutí a operace vložení zřídka a chcete minimalizovat počet otevřené dokumenty a systému windows v váš pracovní prostor, zkuste tuto možnost.  
  
 **Rozpoznat, kdy dojde ke změně souboru mimo prostředí**  
 Pokud je vybraná tato možnost, zobrazí okamžitě upozornění změn k otevření souboru, které byly provedeny podle editoru mimo prostředí IDE. Zpráva umožňuje znovu načíst soubor ze služby storage.  
  
 **Automaticky načíst změny, je-li uložit**  
 Pokud máte **rozpoznat, kdy dojde ke změně souboru mimo prostředí** vybrané a otevření souboru v IDE změny mimo rozhraní IDE, upozornění, je generována ve výchozím nastavení. Pokud tato možnost je povolená, dokument se znovu načíst v rozhraní IDE, má-li vybrat externí změny a bez upozornění se zobrazí.  
  
 **Povolit úpravy souborů jen pro čtení. Upozornit při pokusu o uložení**  
 Pokud je tato možnost povolena můžete otevřít a upravit soubor jen pro čtení. Jakmile budete hotovi, je nutné použít **uložit jako**příkaz k uložení souboru podle nového názvu, pokud chcete uložit záznam změny.  
  
 **Otevřete soubor pomocí adresáře aktuálně aktivní dokument**  
 Pokud vybraná, tato možnost určuje, že **otevření souboru** dialogové okno zobrazí adresáře aktivní dokument. Pokud tato možnost vybrána, **otevřít soubor** dialogové okno zobrazí adresář naposledy použila k otevření souboru.  
  
 **Zkontrolujte konzistentní konce řádků na zatížení**  
 Vyberte tuto možnost editoru prohledávání konce řádků v souboru a zobrazit okno se zprávou, pokud nalezeny nekonzistence v tom, jak jsou formátovány konce řádků.  
  
 **Zobrazení upozornění globální akci zpět upraví upravených souborů**  
 Vyberte tuto možnost zobrazit zprávu, když **globální vrátit zpět** příkaz vrátíte zpět refaktoringu změny provedené v souborech, které se změnily po operace refaktoringu. Vrátilo se do stavu před Refaktoring souboru může zrušit následné změny provedené v souboru.  
  
 **Zobrazit různé soubory v Průzkumníkovi řešení**  
 Výběrem této možnosti zobrazíte **různé soubory** uzlu v **Průzkumníku řešení**. Ostatní soubory jsou soubory, které nejsou přidružené projekt nebo řešení, ale může vyskytovat v **Průzkumníku řešení** pro usnadnění vaší práce.  
  
> [!NOTE]
>  Vyberte tuto možnost, chcete-li povolit **zobrazit v prohlížeči** příkaz na **souboru** nabídku pro webových dokumentů není součástí active webové aplikace.  
  
 **\<** *n*  **> položky uložené v projektu ostatní soubory**  
 Určuje počet souborů pro uchování v **MiscellaneousFiles** složky **Průzkumníku řešení**. Tyto soubory jsou uvedené i v případě, že je již otevřen v editoru. Můžete zadat všechny celé číslo od 0 do 256. Výchozí hodnota je 0.  
  
 Například pokud se tato možnost nastavena na 5 a máte 10 různé soubory otevřené po zavření všech 10 souborů, první 5 stále v zobrazí **různé soubory** složky.  
  
 **Ukládání dokumentů jako Unicode, když data nelze uložit v kódové stránky**  
 Vyberte tuto možnost, způsobit, že soubory obsahující informace, které jsou kompatibilní s vybranou znakovou stránku uložit jako Unicode ve výchozím nastavení.  
  
## <a name="see-also"></a>Viz také  
 [Dialogové okno Možnosti prostředí](../../ide/reference/environment-options-dialog-box.md)   
 [Ostatní soubory](../../ide/reference/miscellaneous-files.md)   
 [Hledání a nahrazení textu](../../ide/finding-and-replacing-text.md)