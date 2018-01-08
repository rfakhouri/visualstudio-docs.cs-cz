---
title: "Postupy: vytvoření nebo aktualizace zásad vrácení se změnami analýzy kódu standardní | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codeanalysis.policyeditor
helpviewer_keywords: code analysis, migrating check-in policy
ms.assetid: 458eb3b8-bb5e-4056-82b7-7079ce9c4089
caps.latest.revision: "29"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d11a8c3169b019ac504ed98258d9281037eb1dd2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-or-update-standard-code-analysis-check-in-policies"></a>Postupy: Vytváření nebo aktualizace standardních zásad vracení se změnami Analýzy kódu
Může vyžadovat, že analýza kódu být spouštěn na všechny projekty kódu v týmového projektu pomocí zásad vrácení se změnami kódu analysis. Vyžadování analýza kódu může zlepšit kvalitu kód, který se změnami do základu kódu.  
  
> [!NOTE]
>  Tato funkce je dostupná pouze v případě, že používáte Team Foundation Server.  
  
 Zásad vrácení se změnami analýzy kódu se nastavují v nastavení projektu týmu a platí pro každý projekt kódu v týmový projekt. Spuštění analýzy kódu jsou nakonfigurované pro projekty kód v souboru projektu (.xxproj) pro projekt kódu. Spuštění analýzy kódu jsou prováděny v místním počítači. Pokud povolíte zásady pro analýzu kódu vrácení se změnami, musí být zkompilovány soubory v projektu kódu, které se mají vrátit se změnami po jejich poslední úpravy a analýza kódu, spuštění, který obsahuje minimálně pravidla v nastavení projektu tým musí být provedeny v počítači kde c hodit změny byly provedeny.  
  
-   Pro spravovaný kód, můžete nastavit zásady, vrácení se změnami zadáním *sadu pravidel* obsahující podmnožinu pravidel analýzy kódu.  
  
-   Pro kód C/C++ zásad vrácení se změnami vyžaduje, že jsou spuštěny všechny pravidel analýzy kódu. Můžete přidat před procesoru direktivy zakázat konkrétní pravidla pro kód jednotlivých projektů v týmových projektech.  
  
 Po zadání zásad vrácení se změnami pro spravovaný kód, můžete synchronizovat členové týmu jejich nastavení analýzy kódu pro kód projekty tak, aby nastavení zásad týmového projektu.  
  
### <a name="to-open-the-check-in-policy-editor"></a>Otevřete editor zásad vrácení se změnami  
  
1.  V nástroji Team Explorer klikněte pravým tlačítkem na název týmového projektu, přejděte na **nastavení projektu Team**a potom klikněte na **správy zdrojového kódu**.  
  
2.  V **správy zdrojového kódu** dialogové okno, vyberte **zásad vrácení se změnami** kartě.  
  
3.  Proveďte jednu z těchto akcí:  
  
    -   Klikněte na tlačítko **přidat** k vytvoření nových zásad vrácení se změnami.  
  
    -   Dvakrát klikněte na existující **analýza kódu** položky v **typ zásad** seznamu můžete změnit zásady.  
  
### <a name="to-set-policy-options"></a>Chcete-li nastavit možnosti zásad  
  
-   Vyberte nebo zrušte zaškrtnutí následující možnosti:  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |**Vynuťte vrácení se změnami tak, aby obsahovala pouze soubory, které jsou součástí aktuální řešení.**|Analýza kódu lze spustit pouze na soubory zadané v konfiguračních souborech na řešení a projektu. Tato zásada zaručuje, že se analýza všech kód, který je součástí řešení.|  
    |**Vynutit analýza kódu C/C++ (/ analyze)**|Vyžaduje, aby se všechny projekty C nebo C++ vytvořené s nástroji / analyze – možnost kompilátoru pro spuštění analýzy kódu, než se můžete vrátit se změnami.|  
    |**Vynutit analýzy kódu pro spravovaný kód**|Vyžaduje, aby všechny spravované projekty spuštění analýzy kódu a sestavení předtím, než se můžete vrátit se změnami.|  
  
-  
  
### <a name="to-specify-a-managed-rule-set"></a>Chcete-li určit sada pravidel spravovaná  
  
-   Z **spuštění této sady pravidel** seznamu, použijte jednu z následujících metod:  
  
    -   Vyberte sadu Microsoft standardního pravidla.  
  
    -   Chcete-li vybrat vlastní sady pravidel, klikněte na tlačítko  **\<vyberte pravidlo nastavené od správy zdrojového kódu... >**a pak zadejte cestu řízení verze pravidlo nastavené v prohlížeči zdroj ovládacího prvku. Syntaxe cesty řízení verze je:  
  
    -   **$/** `TeamProjectName` **/** `VersionControlPath`  
  
    -   Další informace o tom, jak vytvořit a implementovat pravidlo vlastních zásad vrácení se změnami nastavení najdete [implementace vlastních zásad vrácení se změnami pro spravovaný kód](../code-quality/implementing-custom-code-analysis-check-in-policies-for-managed-code.md).  
  
## <a name="see-also"></a>Viz také  
 [Vytváření a používání zásad vrácení se změnami Analýzy kódu](../code-quality/creating-and-using-code-analysis-check-in-policies.md)