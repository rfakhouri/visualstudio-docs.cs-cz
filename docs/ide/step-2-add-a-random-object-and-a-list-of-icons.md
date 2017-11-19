---
title: "Krok 2: Přidejte náhodný objekt a seznam ikon | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95faea28-eddc-4cfa-95fb-3b34b5a976d7
caps.latest.revision: "22"
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: d61602ce6c1542e746f54ecebc8576326e5e6889
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="step-2-add-a-random-object-and-a-list-of-icons"></a>Krok 2: Přidejte náhodný objekt a seznam ikon
V tomto kroku vytvoříte sadu odpovídajících symbolů pro hru. Každý symbol je přidán do dvou náhodných buněk v kontejneru TableLayoutPanel ve formuláři. K tomuto účelu použijete, dva `new` příkazy k vytvoření dvou objektů. První je `Random` objekt, jako jste použili ve hře matematický kvízu s časovým limitem. V tomto kódu slouží k náhodnému výběru buněk v kontejneru TableLayoutPanel. Druhý objekt, který může být pro vás nový, je `List` objekt, který se používá k ukládání náhodně zvolenou symboly.  
  
### <a name="to-add-a-random-object-and-a-list-of-icons"></a>Přidání náhodného objektu a seznamu ikon  
  
1.  V **Průzkumníku řešení**, zvolte **Form1.cs** Pokud používáte Visual C#, nebo **Form1.vb** Pokud používáte Visual Basic a potom na panelu nabídek vyberte **zobrazení** , **Kód**. Jako alternativu můžete zvolit **F7** klíče nebo dvakrát kliknout na **Form1** v **Průzkumníku řešení**.  
  
     Zobrazí se modul kódu pro Form1.  
  
2.  Do stávajícího kódu přidejte následující kód.  
  
     [!code-csharp[VbExpressTutorial4Step2_3_4#1](../ide/codesnippet/CSharp/step-2-add-a-random-object-and-a-list-of-icons_1.cs)]
     [!code-vb[VbExpressTutorial4Step2_3_4#1](../ide/codesnippet/VisualBasic/step-2-add-a-random-object-and-a-list-of-icons_1.vb)]  
  
     Pokud používáte Visual C#, být opravdu vložíte kód po otevření složené závorky a právě po deklaraci třídy (`public partial class Form1 : Form`). Pokud používáte Visual Basic, umístěte kód přímo po deklaraci třídy (`Public Class Form1`).  
  
3.  Při přidávání `List` objektu, Všimněte si **IntelliSense** otevřeném okně. Následuje příklad pro jazyk Visual C#, ale podobný text se zobrazí také při přidávání seznamu v jazyce Visual Basic.  
  
     ![Vlastnosti – okno zobrazení klikněte na událost](../ide/media/express_listintellisense.png "Express_ListIntellisense")  
Okno IntelliSense  
  
    > [!NOTE]
    >  Okno technologie Intellisense se zobrazí pouze v případě, že kód zadáte ručně. Pokud kód zkopírujete a vložíte, nezobrazí se.  
  
     Prohlédnete-li si kód (a poznámky) v malých oddílech, snadněji jim porozumíte. Můžete použít programy `List` objekty ke sledování mnoho různých typů položek. Seznam může obsahovat čísla, hodnoty pravda/nepravda, text nebo jiné objekty. Můžete mít i `List` objekt, který obsahuje jiné `List` objekty. Položky v seznamu se nazývají *elementy*, a každý seznam obsahuje pouze jeden typ elementu. Takže seznam čísel může obsahovat pouze čísla – nelze na něj přidat text. Podobně nelze přidat čísla na seznam hodnot pravda/nepravda.  
  
     Při vytváření `List` pomocí `new` prohlášení, je třeba zadat typ dat, které chcete uložit v ní. To je důvod, proč popis tlačítka v horní části **IntelliSense** okně se zobrazí v seznamu typy elementů. Kromě toho, co je `List<string>` (v jazyce Visual C#) a `List(Of String)` (v jazyce Visual Basic) znamená: je `List` objekt, který obsahuje prvky `string` datového typu. Řetězec je váš program používá k ukládání textu, která je co popisek napravo **IntelliSense** vám sděluje okno.  
  
4.  Zamyslete se nad tím, proč je nutné v jazyce Visual Basic nejprve vytvořit dočasné pole, ale v jazyce Visual C# lze seznam vytvořit pomocí jednoho příkazu. Důvodem je, že má jazyka Visual C# *Inicializátory kolekcí*, který Příprava seznamu tak, aby přijímal hodnoty. V jazyce Visual Basic můžete použít inicializátor kolekce. Avšak z důvodu kompatibility s předchozí verzí jazyka Visual Basic doporučujeme použít předchozí kód.  
  
     Při použití inicializátoru kolekce s `new` příkaz po nové `List` objekt se vytvoří, program se vloží data jste zadali do složených závorek. V takovém případě získáte seznam řetězců s názvem **ikony**, a tento seznam bude inicializován, tak, aby obsahoval šestnáct řetězců. Každý z těchto řetězců je jedno písmeno a všechny odpovídají ikonám, které budou v popiscích. Hra tak bude obsahovat pár vykřičníků, pár velkých písmen N, pár čárek atd. (Pokud jsou tyto znaky nastaveny na písmo Webdings, zobrazí se jako symboly, například jako autobus, kolo, pavouk a atd.) Vaše `List` objekt ve všech, jeden pro každou buňky v panelu TableLayoutPanel bude mít šestnáct řetězců.  
  
    > [!NOTE]
    >  V jazyce Visual Basic získáte stejný výsledek, ale poprvé řetězce do dočasné pole, které je pak převedeno do `List` objektu. Pole je podobné seznamu, s výjimkou, že pole jsou například vytvářena s pevnou velikostí. Seznamy lze zmenšit a zvětšit podle potřeby, což je v tomto programu důležité.  
  
### <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat  
  
-   Chcete-li přejít k dalšímu kroku kurzu, přečtěte si téma [krok 3: náhodné ikony přiřadit každý popisek](../ide/step-3-assign-a-random-icon-to-each-label.md).  
  
-   Chcete-li vrátit k předchozímu kroku kurzu, přečtěte si téma [krok 1: Vytvořte projekt a přidání tabulky do vašeho formuláře](../ide/step-1-create-a-project-and-add-a-table-to-your-form.md).