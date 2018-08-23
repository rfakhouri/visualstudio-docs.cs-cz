---
title: 'Postupy: vytvoření nebo aktualizace standardních zásad analýzy kódu vrácení se změnami | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.codeanalysis.policyeditor
helpviewer_keywords:
- code analysis, migrating check-in policy
ms.assetid: 458eb3b8-bb5e-4056-82b7-7079ce9c4089
caps.latest.revision: 31
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 9f4e834eb02c30bee0fedfa90ddb17d3fa766fb1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669970"
---
# <a name="how-to-create-or-update-standard-code-analysis-check-in-policies"></a>Postupy: Vytváření nebo aktualizace standardních zásad vracení se změnami Analýzy kódu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: vytvoření nebo zásady vrácení se změnami analýzy kódu standardní aktualizace](https://docs.microsoft.com/visualstudio/code-quality/how-to-create-or-update-standard-code-analysis-check-in-policies).  
  
Může vyžadovat spustit analýzu kódu na všechny projekty kódu v týmovém projektu s použitím zásad vracení se změnami kód analýzy. Vyžadování analýzy kódu můžete zlepšit kvalitu kódu, který je vrácen do báze kódu.  
  
> [!NOTE]
>  Tato funkce je dostupná jenom v případě, že používáte Team Foundation Server.  
  
 Zásady vrácení se změnami analýzy kódu se nastavují v nastavení týmového projektu a použít na všech projektů kódu v týmovém projektu. Spuštění analýzy kódu jsou nakonfigurované pro projekty kódu v souboru projektu (.xxproj) pro projekt kódu. Spuštění analýzy kódu jsou prováděny v místním počítači. Pokud povolíte zásady analýzy kódu vrácení se změnami, musí být zkompilovány soubory v projektu kódu, které se mají být vráceny se změnami po jejich poslední úpravy a analýza kódu spuštění, který obsahuje minimálně pravidla v nastavení týmového projektu musí být provedeny v počítači kde jazyka c kající změny byly provedeny.  
  
-   Pro spravovaný kód, nastavíte tak, že určíte zásady vrácení se změnami *sada pravidel, která* , která obsahuje podmnožinu pravidel analýzy kódu.  
  
-   Zásady vrácení se změnami pro kód C/C++ vyžaduje, spuštění všech pravidel analýzy kódu. Můžete přidat processoru direktivy zakázat konkrétní pravidla pro jednotlivé projekty v týmovém projektu.  
  
 Po zadání zásad vrácení se změnami pro spravovaný kód, členové týmu můžete synchronizovat svoje nastavení analýzy kódu pro projekty kódu mají nastavení zásad týmového projektu.  
  
### <a name="to-open-the-check-in-policy-editor"></a>Otevřete editor zásad vrácení se změnami  
  
1.  V Průzkumníku týmových projektů, klikněte pravým tlačítkem na název týmového projektu, přejděte na **nastavení týmového projektu**a potom klikněte na tlačítko **správy zdrojových kódů**.  
  
2.  V **správy zdrojových kódů** dialogové okno, vyberte **zásad vrácení se změnami** kartu.  
  
3.  Proveďte jednu z těchto akcí:  
  
    -   Klikněte na tlačítko **přidat** k vytvoření nové zásady vrácení se změnami.  
  
    -   Dvakrát klikněte na existující **analýzy kódu** položky v **typ zásad** seznamu můžete změnit zásady.  
  
### <a name="to-set-policy-options"></a>Chcete-li nastavit možnosti zásad  
  
-   Zaškrtněte nebo zrušte tyto možnosti:  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |**Vynuťte vrácení se změnami obsahovat soubory, které jsou součástí aktuálního řešení.**|Analýza kódu lze spustit pouze na soubory zadané v konfiguračních souborech na řešení a projektu. Tato zásada zaručuje, že se analyzují veškerý kód, který je součástí řešení.|  
    |**Vynutit analýzu kódu C/C++ (/ analyze)**|Vyžaduje sestavit všechny projekty jazyka C nebo C++ pomocí / analyze – možnost kompilátoru pro spuštění analýzy kódu před jejich mohou být vráceny se změnami.|  
    |**Vynutit analýzu kódu pro spravovaný kód**|Vyžaduje, aby všechny spravované projekty spustit analýzu kódu a sestavení, než se mohou být vráceny se změnami.|  
  
-  
  
### <a name="to-specify-a-managed-rule-set"></a>Chcete-li určit sada pravidel spravovaná  
  
-   Z **spustit tuto sadu pravidel** seznamu, použijte jednu z následujících metod:  
  
    -   Vyberte sadu standardních pravidel společnosti Microsoft.  
  
    -   Chcete-li vybrat vlastní sady pravidel, klikněte na tlačítko  **\<vybrat sadu pravidel ze správy zdrojového kódu... >** a pak zadejte cestu správy verzí sady pravidel, která v prohlížeči zdrojového ovládacího prvku. Syntaxe cestu správy verzí je následující:  
  
    -   **$/** `TeamProjectName` **/** `VersionControlPath`  
  
    -   Další informace o tom, jak vytvořit a implementovat vlastní zásady vrácení se změnami sady, naleznete v tématu [implementace vlastních zásad vrácení se změnami pro spravovaný kód](../code-quality/implementing-custom-code-analysis-check-in-policies-for-managed-code.md).  
  
## <a name="see-also"></a>Viz také  
 [Vytváření a používání zásad vrácení se změnami Analýzy kódu](../code-quality/creating-and-using-code-analysis-check-in-policies.md)



