---
title: "Zabezpečení v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 02/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code access security, coding errors
- security [.NET Framework], about security
ms.assetid: 318c34ce-f643-468c-83a1-843196f5d845
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c9d546d4020cb9a8e73efdea77fdb85d77d6146d
ms.sourcegitcommit: a07b789cc41ed72664f2c700c1f114476e7b0ddd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/19/2018
---
# <a name="security-in-visual-studio"></a>Zabezpečení v sadě Visual Studio

Zabezpečení byste měli věnovat pozornost ve všech aspektech vývoje aplikace od návrhu až po nasazení. Spusťte jako bezpečně spuštěním sady Visual Studio. V tématu [oprávnění uživatele](../ide/user-permissions-and-visual-studio.md).  
  
 Abyste mohli efektivně vyvíjet bezpečné aplikace, měli byste znát základní principy konceptů zabezpečení a funkce zabezpečení platforem, pro které vyvíjíte. Také je třeba porozumět bezpečným technikám kódování.  
  
## <a name="understanding-security"></a>Princip zabezpečení  
 [Zabezpečení](/dotnet/standard/security/index)  
 Popisuje zabezpečení přístupu ke kódu rozhraní .NET Framework, zabezpečení založené na rolích, zásady zabezpečení a nástroje zabezpečení.  
  
 [Bránit kódu s tipy prvních deset zabezpečení, které musí vědět každý vývojář](http://go.microsoft.com/fwlink/?LinkId=72877)  
 Popisuje problémy, na které je třeba dávat pozor, abyste neohrozili svá data nebo systém.  
  
## <a name="coding-for-security"></a>Kódování pro zabezpečení  
 Většina chyb kódování, které mají za následek ohrožení zabezpečení, je způsobena nesprávnými úvahami vývojářů při práci s uživatelským vstupem nebo tím, že vývojáři plně nerozumí platformě, pro kterou vyvíjejí.  
  
 [Pokyny pro zabezpečené kódování](/dotnet/standard/security/secure-coding-guidelines)  
 Obsahuje pokyny pro klasifikaci komponent k odstranění problémů zabezpečení.  
  
 [Osvědčené postupy zabezpečení](/cpp/top/security-best-practices-for-cpp)  
 Pojednává o přetečení vyrovnávací paměti a poskytuje přehled o funkci kontroly zabezpečení pro jazyk Microsoft Visual C++, kterou přináší příznak /GS pro kompilaci.

## <a name="building-for-security"></a>Vytváření pro zabezpečení  
 Zabezpečení je také důležitý faktor v procesu sestavení.  Pár dalších kroků můžete zlepšit zabezpečení nasazené aplikace a pomáhá zabránit neoprávněnému zpětnou analýzu, falšování identity nebo jiným útokům.

 [Dotfuscator Community Edition (CE)](dotfuscator/index.md)  
 Vysvětluje, jak nastavit a začít používat bezplatnou preemptivní ochranu - Dotfuscatoru Community Edition k ochraně sestavení .NET z zpětnou a neoprávněnému použití (například neoprávněným ladění).
  
 [Správa sestavení a podepsání manifestu](managing-assembly-and-manifest-signing.md)  
 Popisuje podepisování silného názvu, který můžete použít k jednoznačné identifikaci softwarové komponenty, brání falšování.