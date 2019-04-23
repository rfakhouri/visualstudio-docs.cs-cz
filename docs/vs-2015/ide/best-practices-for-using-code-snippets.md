---
title: Osvědčené postupy pro používání fragmentů kódu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- code snippets, best practices
- code snippets, security
ms.assetid: a293ec17-4dd7-4a99-8eeb-99f44a822a8b
caps.latest.revision: 26
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 60d41398a37870d8be7a55003259b7cb2b9e48db
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60099621"
---
# <a name="best-practices-for-using-code-snippets"></a>Doporučené postupy pro používání fragmentů kódu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Kód ve fragmentu kódu zobrazuje pouze základní způsob, jak něco udělat. Pro většinu aplikací musí změnit kód tak, aby odpovídala aplikace.  
  
## <a name="handling-exceptions"></a>Zpracování výjimek  
 Obvykle fragment kódu Try... Bloky catch zachycují a znovu vyvolat všechny výjimky. Který nemusí být správnou volbou pro váš projekt. Pro každou výjimku existuje několik způsobů, jak reagovat. Příklady najdete v tématu [jak: Zpracování výjimky pomocí bloku try/catch (C# Programming Guide)](http://msdn.microsoft.com/library/ca8e3773-980e-4767-8633-7408540e9818) a [zkuste... Catch... Příkaz finally](http://msdn.microsoft.com/library/d6488026-ccb3-42b8-a810-0d97b9d6472b).  
  
## <a name="file-locations"></a>Umístění souborů  
 Při umístění souborů můžete přizpůsobit pro vaši aplikaci, byste uvažovat o následujícím:  
  
- Hledání na dostupném místě. Nemusí mít uživatelé přístup ke složce Program Files počítači, a proto ukládání souborů pomocí souborů aplikace nemusí fungovat.  
  
- Hledání na bezpečném místě. Ukládání souborů v kořenové složce (C:\\) není zabezpečený. Pro data aplikací doporučujeme \Application složku Data. Pro data jednotlivých uživatelů může aplikace vytvořit soubor pro každého uživatele ve složce Dokumenty \My.  
  
- Pomocí platný název souboru. Můžete použít <xref:System.Windows.Forms.OpenFileDialog> a <xref:System.Windows.Forms.SaveFileDialog> ovládacích prvků pro snížení pravděpodobnosti výskytu neplatné názvy souborů. Mějte na paměti, že mezi časem uživatel vybere soubor a čas, váš kód zpracovává soubor, mohou odstranit soubor. Kromě toho uživatel nemá oprávnění k zápisu do souboru.  
  
## <a name="security"></a>Zabezpečení  
 Zabezpečené fragment je závisí na jeho použití ve zdrojovém kódu a jak je změnit, až bude v kódu. Následující seznam obsahuje několik oblastí, které musíte vzít v úvahu.  
  
- Přístup k souboru a databáze  
  
- Zabezpečení přístupu kódu  
  
- Ochrana prostředků (jako jsou protokoly událostí, registr)  
  
- Ukládání tajných klíčů  
  
- Ověřuje se, jestli vstupy  
  
- Předávání dat skriptovací technologie  
  
  Další informace najdete v tématu [zabezpečení aplikací](../ide/securing-applications.md).  
  
## <a name="downloaded-code-snippets"></a>Fragmenty kódu stažené  
 Fragmenty kódu technologie IntelliSense ve Visual Studio nainstalované nejsou v samotných ohrožení zabezpečení. Může ale vytvořit bezpečnostní rizika ve vaší aplikaci. Fragmenty kódu stažené z Internetu měli zacházet jako s další obsah stažený – s nejvyšší opatrností.  
  
- Stáhnout fragmenty pouze z lokality, které důvěřujete a použít aktuální antivirový software.  
  
- Otevřít všechny soubory stažené fragmentu kódu v programu Poznámkový blok nebo editoru XML sady Visual Studio a pečlivě zkontrolujte před instalací. Vyhledejte následující problémy:  
  
    - Fragment kódu by mohl poškodit váš systém, pokud je spuštěn. Pečlivě si přečtěte zdrojový kód před jejím spuštěním.  
  
    - Adresa URL nápovědy blok fragment souboru může obsahovat adresy URL, které spustit škodlivý soubor nebo zobrazit urážlivé webu.  
  
    - Fragment kódu mohou obsahovat odkazy, které jsou tiše přidány do projektu a mohou být načteny z kdekoli ve vašem systému. Tyto odkazy může být stažené do vašeho počítače ze kterého jste stáhli fragmentu kódu. Fragment kódu může proveďte volání metody v odkazu, který se spustí škodlivý kód. Chránit proti takového útoku, najdete v tématu importy a odkazy na bloky souboru fragmentu kódu.  
  
## <a name="see-also"></a>Viz také  
 [Fragmenty kódu technologie IntelliSense jazyka Visual Basic](http://msdn.microsoft.com/library/ffdde4c9-8141-4906-b09b-15181357a643)   
 [Zabezpečení aplikací](../ide/securing-applications.md)   
 [Fragmenty kódu](../ide/code-snippets.md)
