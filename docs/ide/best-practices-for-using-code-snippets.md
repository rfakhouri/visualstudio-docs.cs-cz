---
title: "Osvědčené postupy pro používání fragmentů kódu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code snippets, best practices
- code snippets, security
ms.assetid: a293ec17-4dd7-4a99-8eeb-99f44a822a8b
caps.latest.revision: "22"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 34424ae13a47008eaefa3634f2bf25d31daf285e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="best-practices-for-using-code-snippets"></a>Doporučené postupy pro používání fragmentů kódu
Kód v fragment kódu ukazuje jenom nejzákladnější způsob, jak něco udělat. Pro většinu aplikací musíte změnit kód tak, aby vyhovovala aplikace.  
  
## <a name="handling-exceptions"></a>Zpracování výjimek  
 Obvykle fragment kódu Try... Catch – bloky catch a opětovné všechny výjimky. Která nemusí být správná volba pro váš projekt. Pro každý výjimky existuje několik způsobů reagovat. Příklady najdete v tématu [postupy: zpracování výjimky pomocí bloku try/catch (C# Průvodce programováním)](/dotnet/csharp/programming-guide/exceptions/how-to-handle-an-exception-using-try-catch) a [zkuste... Catch... Finally – příkaz](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement).  
  
## <a name="file-locations"></a>Umístění souborů  
 Pokud se vaše aplikace přizpůsobit umístění souborů, musí si myslíte o následující:  
  
-   Hledání na dostupném místě. Uživatelé nemusí mít přístup ke složce Program Files počítače, tak ukládání souborů s souborů aplikace nemusí fungovat.  
  
-   Hledání v zabezpečeném umístění. Ukládání souborů v kořenové složce (C:\\) není zabezpečený. Pro data aplikací doporučujeme složka \Application Data. Pro jednotlivé uživatele data aplikace, můžete vytvořit soubor pro každého uživatele ve složce Dokumenty \My.  
  
-   Pomocí platný název souboru. Můžete použít <xref:System.Windows.Forms.OpenFileDialog> a <xref:System.Windows.Forms.SaveFileDialog> ovládací prvky, které sníží pravděpodobnost neplatné názvy souborů. Upozorňujeme, že mezi časem uživatel vybere soubor a čas kódu manipuluje souboru, soubor budou odstraněny. Kromě toho uživatel nemusí mít oprávnění k zápisu do souboru.  
  
## <a name="security"></a>Zabezpečení  
 Do jaké míry je fragment závisí na tom, jak je upravována, po v kódu a kde se používá ve zdrojovém kódu. Následující seznam obsahuje několik oblastí, které musí vzít v úvahu.  
  
-   Přístup k souboru a databáze  
  
-   Zabezpečení přístupu kódu  
  
-   Ochrana prostředků (například protokoly událostí registru)  
  
-   Ukládání tajné klíče  
  
-   Ověření vstupy  
  
-   Předávání dat skriptovací technologie  
  
 Další informace najdete v tématu [zabezpečení aplikací](../ide/securing-applications.md).  
  
## <a name="downloaded-code-snippets"></a>Fragmenty kódu stažené  
 Nainstalovat Visual Studio IntelliSense – fragmenty kódu nejsou v samotných riziko zabezpečení. Však mohou vytvářet rizika zabezpečení ve vaší aplikaci. Fragmenty kódu stažené z Internetu zacházeno jako jiný obsah stažený - s velmi opatrní.  
  
-   Stáhněte fragmenty pouze z webů, které důvěřujete a pomocí aktuálního antivirového softwaru.  
  
-   Všechny soubory stažené fragment kódu otevřete v poznámkovém bloku nebo editoru XML sady Visual Studio a zkontrolovat si důkladně před jejich instalací. Podívejte se na následující problémy:  
  
    -   Fragment kódu může poškodit systém, pokud ho provést. Pečlivě si přečtěte před spuštěním ve zdrojovém kódu.  
  
    -   Blok pomůže adresu URL souboru fragment kódu může obsahovat adresy URL, které provést soubor skriptu škodlivý nebo zobrazit urážlivé webové stránky.  
  
    -   Fragment mohou obsahovat odkazy, které jsou přidány bezobslužně do projektu a může být načten z libovolné místo v systému. Tyto odkazy mohou byly staženy do počítače ze které jste stáhli fragmentu. Proveďte fragmentu může volat metodu v odkazu, který provede škodlivý kód. Za účelem ochrany proti takové napadení, zkontrolujte importy a odkazy na bloky souboru fragment kódu.  
  
## <a name="see-also"></a>Viz také  
 [Fragmenty kódu technologie IntelliSense v jazyce Visual Basic](/dotnet/visual-basic/developing-apps/using-ide/intellisense-code-snippets)   
 [Zabezpečení aplikací](../ide/securing-applications.md)   
 [Fragmenty kódu](../ide/code-snippets.md)