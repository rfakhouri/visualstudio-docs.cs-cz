---
title: 'Návrhář pracovního postupu: Definice a používání delegátů aktivit'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c68e42ad-3ec0-4c2d-b104-fe36c6d83b5e
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 34cb06bbc5c9575f5a10507a8015c9819e7b533b
ms.sourcegitcommit: ba5e072c9fedeff625a1332f22dcf3644d019f51
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/31/2019
ms.locfileid: "66431798"
---
# <a name="how-to-define-and-consume-activity-delegates-in-the-workflow-designer"></a>Postupy: Definování a použití delegátů aktivit v návrháři postupu provádění

Rozhraní .NET framework 4.5 zahrnuje návrháře out-of-box <xref:System.Activities.Statements.InvokeDelegate> aktivity. Tento návrhář je možné přiřadit delegáty aktivity, které jsou odvozeny z <xref:System.Activities.ActivityDelegate>, jako například <xref:System.Activities.ActivityAction> nebo <xref:System.Activities.ActivityFunc%601>.

## <a name="define-an-activity-delegate"></a>Definovat na delegáta aktivity

1. Vytvořte nový **Konzolová aplikace pracovního postupu** projektu.

   > [!NOTE]
   > Pokud se nezobrazí **pracovního postupu** šablony projektu, nejprve nainstalujte **Windows Workflow Foundation** komponentu sady Visual Studio. Podrobné pokyny najdete v tématu [nainstalovat Windows Workflow Foundation](developing-applications-with-the-workflow-designer.md#install-windows-workflow-foundation).

3. Klikněte pravým tlačítkem na projekt v **Průzkumníka řešení** a vyberte **přidat** > **nová položka**. Vyberte **pracovního postupu** kategorie a pak vyberte **aktivity** šablony položky. Pojmenujte novou aktivitu **MyForEach.xaml** a pak vyberte **OK**.

   Aktivity se otevře v Návrháři pracovních postupů.

4. V Návrháři postupu provádění, klikněte **argumenty** kartu.

5. Klikněte na tlačítko **vytvořit Argument**. Pojmenujte novou argument **položky**.

6. V **typ argumentu** sloupci vyberte **pole [T]** .

7. V typu prohlížeče, vyberte **objekt** a pak vyberte **OK**.

8. Klikněte na tlačítko **vytvořit Argument** znovu. Pojmenujte novou argument **tělo**. V **směr** sloupci pro argument nový, vyberte **vlastnost**.

9. Ve sloupci Typ argumentu vyberte **vyhledat typy**

10. V prohlížeči typu zadejte **ActivityAction** v **název typu** pole. Vyberte **ActivityAction\<T >** ve stromovém zobrazení. Vyberte **objekt** v rozevírací nabídce, která se zobrazí přiřadit typ **ActivityAction\<objektu >** na argument.

11. Přetáhněte <xref:System.Activities.Statements.While> aktivita z **tok řízení** části panelu nástrojů na plochu návrháře.

12. Vyberte <xref:System.Activities.Statements.While> aktivitu a vyberte **proměnné** kartu.

13. Vyberte **vytvořit proměnnou**. Pojmenujte novou proměnnou **Index**.

14. V **typ proměnné** sloupci vyberte **Int32**. Nechte **oboru** jako **při**a **výchozí** sloupce prázdné.

15. Nastavte **podmínku** vlastnost <xref:System.Activities.Statements.While> aktivitu **index < Items.Length;** .

16. Přetáhněte <xref:System.Activities.Statements.InvokeDelegate> aktivita z **primitiv** části panelu nástrojů **tělo** z <xref:System.Activities.Statements.While> aktivity.

17. Vyberte **tělo** v rozevíracím seznamu delegáta.

18. V **vlastnosti** mřížky <xref:System.Activities.Statements.InvokeDelegate> aktivity, klikněte na tlačítko **...**  tlačítko **argumenty delegátů** vlastnost.

19. V **hodnotu** sloupec argument s názvem **Argument**, zadejte **položky [Index]** . Klikněte na tlačítko **Ok** zavřete **DelegateArguments** dialogového okna.

20. Přetáhněte <xref:System.Activities.Statements.Assign> aktivity na vodorovnou čáru pod <xref:System.Activities.Statements.InvokeDelegate> aktivity. <xref:System.Activities.Statements.Assign> Vytvoření aktivity a <xref:System.Activities.Statements.Sequence> aktivity se vytvoří automaticky obsahovat dvě aktivity v **tělo** část **MyForEach** aktivity. Sekvence je vyžadováno, protože **tělo** oddíl může obsahovat pouze jednu aktivitu. Automaticky vytváří nové <xref:System.Activities.Statements.Sequence> aktivity je nová funkce rozhraní .NET Framework 4.5.

21. Nastavte **k** vlastnost <xref:System.Activities.Statements.Assign> aktivitu **index**. Nastavte **hodnotu** vlastnost **přiřadit** aktivitu **index + 1**.

    Vlastní **MyForEach** aktivita vyvolá aktivitu libovolného jednou pro každou hodnotu předanou do něj prostřednictvím **položky** kolekce s hodnotami v kolekci jako vstupy pro aktivitu.

## <a name="use-the-custom-activity-in-a-workflow"></a>Použití vlastní aktivity v pracovním postupu

1. Sestavte projekt stisknutím kombinace kláves **Ctrl**+**Shift**+**B**.

2. V **Průzkumníka řešení**, otevřete **Workflow1.xaml** v návrháři.

3. Přetáhněte **MyForEach** aktivitu z panelu nástrojů na plochu návrháře. Aktivita je v části nástrojů se stejným názvem jako projekt.

4. Nastavte **položky** vlastnost **MyForEach** aktivitu **nové Object [] {1, "abc"}** .

5. Přetáhněte <xref:System.Activities.Statements.WriteLine> aktivita z **primitiv** části panelu nástrojů **delegáta: Body** část **MyForEach** aktivity.

6. Nastavte **Text** vlastnost <xref:System.Activities.Statements.WriteLine> aktivitu **Argument.ToString()** .

Při spuštění pracovního postupu se konzola zobrazí následující výstup:

**1**
**abc**