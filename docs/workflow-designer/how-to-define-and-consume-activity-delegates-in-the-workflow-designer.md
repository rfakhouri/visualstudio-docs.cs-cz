---
title: 'Návrhář postupu provádění - postupy: definice a používání delegátů aktivity'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: c68e42ad-3ec0-4c2d-b104-fe36c6d83b5e
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 2039c1792a5e42c3181a01b10ff5bf271ea3bf2f
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2018
ms.locfileid: "36755753"
---
# <a name="how-to-define-and-consume-activity-delegates-in-the-workflow-designer"></a>Postupy: definice a používání delegátů aktivity v Návrháři pracovních postupů

Rozhraní .NET framework 4.5 zahrnuje out-of-box designer pro aplikaci <xref:System.Activities.Statements.InvokeDelegate> aktivity. Tento návrhář lze přiřadit delegáty pro aktivity, které pocházejí z <xref:System.Activities.ActivityDelegate>, jako například <xref:System.Activities.ActivityAction> nebo <xref:System.Activities.ActivityFunc%601>.

## <a name="define-an-activity-delegate"></a>Definování delegáta aktivity

1.  V sadě Visual Studio, vyberte **soubor** > **nový** > **projektu**.

1. V **nový projekt** dialogové okno, vyberte **pracovního postupu** kategorie na levé straně a pak vyberte **pracovního postupu konzolové aplikace** šablona projektu. Název projektu (v případě potřeby) a klikněte na tlačítko **Ok**.

   > [!NOTE]
   > Pokud nevidíte **pracovního postupu** kategorie, první instalaci **modelu Windows Workflow Foundation** součást produktu Visual Studio 2017. Podrobné pokyny najdete v tématu [nainstalovat Windows Workflow Foundation](developing-applications-with-the-workflow-designer.md#install-windows-workflow-foundation).

2.  Klikněte pravým tlačítkem na projekt v **Průzkumníku řešení** a vyberte **přidat** > **novou položku**. Vyberte **pracovního postupu** kategorie a potom vyberte **aktivity** šablony položky. Název nové aktivity **MyForEach.xaml** a pak vyberte **OK**.

   Otevře se aktivity v Návrháři pracovních postupů.

3.  V Návrháři pracovních postupů, klikněte **argumenty** kartě.

4.  Klikněte na tlačítko **vytvořit Argument**. Název nové argument **položky**.

5.  V **typ argumentu** sloupce, vyberte **pole [T]**.

6.  V prohlížeči typu, vyberte **objekt** a pak vyberte **OK**.

7.  Klikněte na tlačítko **vytvořit Argument** znovu. Název nové argument **textu**. V **směr** sloupec pro nové argument, vyberte **vlastnost**.

8.  Ve sloupci Typ argumentu vyberte **Procházet pro typy**

9. V prohlížeči typ zadejte **ActivityAction** v **název typu** pole. Vyberte **ActivityAction\<T >** ve stromovém zobrazení. Vyberte **objekt** v rozevírací nabídce, který se zobrazí přiřadit typ **ActivityAction\<objekt >** k argumentu.

10. Přetáhněte <xref:System.Activities.Statements.While> aktivity z **tok řízení** oddílu na panelu na plochu návrháře.

11. Vyberte <xref:System.Activities.Statements.While> aktivitu a vyberte **proměnné** kartě.

12. Vyberte **vytvořit proměnnou**. Název nové proměnné **Index**.

13. V **typ proměnné** sloupce, vyberte **Int32**. Ponechte **oboru** jako **při**a **výchozí** sloupec prázdné.

14. Nastavte **podmínku** vlastnost <xref:System.Activities.Statements.While> aktivitu **index < Items.Length;**.

15. Přetáhněte <xref:System.Activities.Statements.InvokeDelegate> aktivity z **primitiv** oddílu na panelu na **textu** z <xref:System.Activities.Statements.While> aktivity.

16. Vyberte **textu** v rozevíracím seznamu delegáta.

17. V **vlastnosti** mřížky pro <xref:System.Activities.Statements.InvokeDelegate> aktivity, klikněte **...**  v tlačítko **delegáta argumenty** vlastnost.

18. V **hodnotu** sloupec s názvem argumentu **Argument**, zadejte **položky [Index]**. Klikněte na tlačítko **Ok** zavřete **DelegateArguments** dialogové okno.

19. Přetáhněte <xref:System.Activities.Statements.Assign> aktivity na vodorovném řádku pod <xref:System.Activities.Statements.InvokeDelegate> aktivity. <xref:System.Activities.Statements.Assign> Vytvoření aktivity a <xref:System.Activities.Statements.Sequence> aktivity se vytvoří automaticky tak, aby obsahovala dvě aktivity v **textu** části **MyForEach** aktivity. Pořadí je potřeba od **textu** oddílu může obsahovat pouze jednu aktivitu. Automaticky vytvoří nový <xref:System.Activities.Statements.Sequence> aktivity je nová funkce rozhraní .NET Framework 4.5.

20. Nastavte **k** vlastnost <xref:System.Activities.Statements.Assign> aktivitu **index**. Nastavte **hodnotu** vlastnost **přiřadit** aktivitu **index + 1**.

   Vlastní **MyForEach** aktivity vyvolá aktivitu libovolný jednou pro každou hodnotu předané do jeho prostřednictvím **položky** kolekce s hodnotami v kolekci jako vstupy pro aktivitu.

## <a name="use-the-custom-activity-in-a-workflow"></a>Použít vlastní aktivity v pracovním postupu

1.  Sestavení projektu stisknutím **Ctrl**+**Shift**+**B**.

2.  V **Průzkumníku řešení**, otevřete **Workflow1.xaml** v návrháři.

3.  Přetáhněte **MyForEach** aktivity z panelu nástrojů na plochu návrháře. Aktivita je v části sada nástrojů se stejným názvem jako projekt.

4.  Nastavte **položky** vlastnost **MyForEach** aktivitu **nový objekt [] {1, "abc"}**.

5.  Přetáhněte <xref:System.Activities.Statements.WriteLine> aktivity z **primitiv** oddílu na panelu na **delegáta: Body** části **MyForEach** aktivity.

6.  Nastavte **Text** vlastnost <xref:System.Activities.Statements.WriteLine> aktivitu **Argument.ToString()**.

Po provedení pracovního postupu se konzola zobrazí následující výstup:

**1**
**abc**