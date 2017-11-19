---
title: "Hierarchie volání | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.CallHierarchy
helpviewer_keywords: Call Hierarchy
ms.assetid: c55bda01-d7de-4823-8f9a-1bcc37dbb74a
caps.latest.revision: "40"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 065806ec223273bbacba6da7702f21bc25510983
ms.sourcegitcommit: c0422a3d594ea5ae8fc03f1aee684b04f417522e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/02/2017
---
# <a name="call-hierarchy"></a>Hierarchie volání
Hierarchie volání umožňuje procházet kódu pomocí zobrazení všechna volání do a z vybrané metoda, vlastnost nebo konstruktor. Díky tomu můžete lépe pochopit tok kódu a vyhodnotit vliv změn kódu. Můžete zkontrolovat několik úrovní kódu zobrazíte komplexní řetězy volání metod a další vstupní body na kód, který umožňuje, abyste mohli prozkoumat všechny možné provádění cesty.  
  
 Hierarchie volání je k dispozici v době návrhu, na rozdíl od zásobníku volání, který se zobrazí při ladicího programu.  
  
## <a name="using-call-hierarchy"></a>Použití hierarchie volání  
 Chcete-li zobrazit **hierarchie volání** oken, klikněte pravým tlačítkem na název metoda, vlastnost nebo volání konstruktoru a pak klikněte na tlačítko **zobrazení hierarchie volání**.  
  
 Název člena je zobrazen v podokně zobrazení stromu v **hierarchie volání** okno. Pokud rozbalíte uzlu člen **volání do***název člena* a **volání z***název člena* zobrazí podřízených uzlů. Následující obrázek znázorňuje tyto uzly v **hierarchie volání** okno.  
  
 ![Hierarchie volání s jedním uzlem otevřete](../../ide/reference/media/onenode.png "OneNode")  
Hierarchie volání – okno  
  
-   Pokud rozbalíte **volání do** uzlu, všechny členy, že se zobrazují volání vybraného člena.  
  
-   Pokud rozbalíte **volání z** zobrazují v uzlu všechny členy, kteří jsou volány vybraného člena.  
  
Můžete rozbalit každý z těchto poduzlem členů do **volání do** a **volání z** uzlů. To umožňuje přejděte do zásobníku volající, jak je znázorněno na následujícím obrázku.  
  
![Hierarchie volání více uzlů otevřete](../../ide/media/multiplenodes.png "MultipleNodes")  
Hierarchie volání – okno  
  
Pro členy, které jsou definovány jako virtuální nebo abstraktní **název metody přepsání** uzel se objeví. Pro členy rozhraní **název metody implementuje** uzel se objeví. Tyto uzly rozšíření se zobrazí na stejné úrovni jako **volání do** a **volání z** uzlů.  
  
**Obor vyhledávání** na panelu nástrojů obsahuje možnosti pro **Moje řešení**, **aktuálního projektu**, a **aktuálním dokumentu**.  
  
Když vyberete podřízený člen v **hierarchie volání** podokno se stromovým zobrazením:  
  
-   **Hierarchie volání** podokně podrobností se zobrazí všechny řádky kódu, ve kterém je daný člen podřízené volána z nadřazeného člena.  
  
-   **Definice kódu – okno**, pokud je otevřené, zobrazí kód pro vybraného člena. Toto okno je k dispozici v C# a C++. Další informace o tomto okně najdete v tématu [zobrazení struktury kódu](../../ide/viewing-the-structure-of-code.md).  
  
> [!NOTE]
>  Hierarchie volání není nalezena metoda odkazy skupiny zahrnující míst, kde se přidá jako obslužné rutiny události metodu, nebo je přiřazená delegáta. Pokud chcete najít všechny odkazy na metodu, můžete použít **najít všechny odkazy** příkaz.  
  
## <a name="shortcut-menu-items"></a>Položky místní nabídky  
 Následující tabulka popisuje několik možnosti místní nabídky, které jsou k dispozici, když kliknete pravým tlačítkem na uzel v podokně zobrazení stromu.  
  
|Položky kontextové nabídky|Popis|  
|-----------------------|-----------------|  
|**Přidat jako nový kořen**|Přidá vybraný uzel do podokna zobrazení stromu jako nový kořenový uzel. To umožňuje zaměřit se na konkrétní podstrom vaši pozornost.|  
|**Odebrat kořenové**|Odebere vybraného kořenového uzlu z podokna zobrazení stromu. Tato možnost je dostupná pouze z kořenového uzlu.<br /><br /> Můžete také **odebrat kořenové** tlačítka panelu nástrojů k odebrání vybrané kořenového uzlu.|  
|**Přechod na definici**|Spustí příkaz Přejít k definici na vybraný uzel. Umožňuje přejít k původní definici pro volání člena nebo definicí proměnné.<br /><br /> Spustit příkaz Přejít k definici, můžete také dvakrát klikněte na vybraný uzel nebo stiskněte klávesu F12 na vybraný uzel.|  
|**Najít všechny odkazy**|Spustí příkaz Najít všechny odkazy na vybraný uzel. To tento odkaz třída nebo člen vyhledá všechny řádky kódu v projektu.<br /><br /> SHIFT + F12 také můžete spustit příkaz Najít všechny odkazy na vybraný uzel.|  
|**Kopírování**|Zkopíruje obsah vybraného uzlu (ale ne jeho podřízené uzly).|  
|**Aktualizace**|Sbalí vybraného uzlu tak, aby znovu rozšíření se zobrazí aktuální informace.|