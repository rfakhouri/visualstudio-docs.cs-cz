---
title: 'Postupy: přizpůsobení diagramů tříd (návrhář tříd) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- class diagrams, customizing
- shapes, removing type from class diagrams
- type shapes, removing from class diagrams
- class diagrams, removing type shapes
ms.assetid: e9030aea-c77d-4cc1-b8f6-b6ca469b692d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5a2f58626008ba50f436f7836fe13ca92fcce155
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-customize-class-diagrams-class-designer"></a>Postupy: Přizpůsobení diagramů tříd (návrhář tříd)
Můžete změnit způsob, jak diagramy tříd zobrazují informace. Můžete přizpůsobit celý diagram nebo jednotlivé typy na ploše návrhu.  
  
Můžete například upravit úroveň zvětšení celého diagramu tříd, změnit způsob seskupování a řazení jednotlivých členů typu, skrýt nebo zobrazit vztahy a přesunout jednotlivé typy nebo množiny typů kamkoli v diagramu.  
  
> [!NOTE]
>  Upravením způsobu, jakým se tvary v diagramu zobrazují, nezměníte základní kód pro typy znázorněné v diagramu.  
  
Části, které obsahují členy typu, jako je například část Vlastnosti ve třídě, se nazývají oddíly. Jednotlivé oddíly a členy typu můžete skrýt nebo zobrazit.  
  
**V tomto tématu**  
  
-   [Oddálit diagramu tříd](how-to-customize-class-diagrams.md#ZoomInOut)  
  
-   [Přizpůsobení seskupování a řazení členy typu](how-to-customize-class-diagrams.md#CustomizeGroupingSorting)  
  
-   [Skrýt přihrádky pro typ](how-to-customize-class-diagrams.md#HideCompartments)  
  
-   [Skrýt jednotlivé členy typu](how-to-customize-class-diagrams.md#HideMembers)  
  
-   [Zobrazit skrytá přihrádky a členy typu](how-to-customize-class-diagrams.md#DisplayHiddenCompartmentsAndMemberrs)  
  
-   [Skrýt relace](how-to-customize-class-diagrams.md#HideAssociationAndInheritance)  
  
-   [Zobrazit skrytá relace](how-to-customize-class-diagrams.md#DisplayAssociationAndInheritance)  
  
-   [Odstranění obrazce z diagramu – třída](how-to-customize-class-diagrams.md#RemoveCodeAndShape)  
  
-   [Odstranit obrazce typu a jeho základní kódu](how-to-customize-class-diagrams.md#DeleteTypeShapeAndCode)  
  
##  <a name="ZoomInOut"></a> Oddálit diagramu tříd  
  
1.  Otevřete a vyberte soubor diagramu tříd v Návrháři tříd.  
  
2.  Na panelu nástrojů návrhář tříd, klikněte na **zvětšení v** nebo **Oddálit** tlačítko změnit úroveň přiblížení plochu návrháře.  
  
     or  
  
     Zadejte hodnotu přiblížení. Můžete použít **zvětšení** rozevíracím seznamu nebo zadejte platný přiblížení úroveň (platný rozsah je od 10 % až 400 %).  
  
    > [!NOTE]
    >  Změna úrovně přiblížení neovlivní měřítko výtisku vašeho diagramu tříd.  
  
##  <a name="CustomizeGroupingSorting"></a> Přizpůsobení seskupování a řazení členy typu  
  
1.  Otevřete a vyberte soubor diagramu tříd v Návrháři tříd.  
  
2.  Klikněte pravým tlačítkem myši na prázdnou oblast na návrhovou plochu a přejděte na **členy skupiny**.  
  
3.  Vyberte jednu z dostupných možností:  
  
    1.  **Seskupit podle druhu** odděluje jednotlivé typ členy do seskupené seznam vlastností, metody, události a pole. Jednotlivé skupiny závisí na definici entit: třída například nebude zobrazovat žádnou skupinu událostí, pokud pro danou třídu zatím nebyly definovány žádné události.  
  
    2.  **Seskupit podle přístup** odděluje jednotlivé typ členů do seznamu seskupené podle člena přístup modifikátory. Například veřejné a soukromé.  
  
    3.  **Seřadit podle abecedy** zobrazí položky, které tvoří entitu jako jeden abecední seznam. Seznam je seřazen vzestupně.  
  
##  <a name="HideCompartments"></a> Skrýt přihrádky pro typ  
  
1.  Otevřete a vyberte soubor diagramu tříd v Návrháři tříd.  
  
2.  Klikněte pravým tlačítkem na kategorii členů v typu, který chcete přizpůsobit (například vyberte **metody** uzlu v třídě.  
  
3.  Klikněte na tlačítko **skrýt prostředí**.  
  
     Vybraný oddíl zmizí z kontejneru typu.  
  
##  <a name="HideMembers"></a> Skrýt jednotlivé členy typu  
  
1.  Otevřete a vyberte soubor diagramu tříd v Návrháři tříd.  
  
2.  Klikněte pravým tlačítkem myši na člen v typu, který chcete skrýt.  
  
3.  Klikněte na tlačítko **skrýt**.  
  
     Vybraný člen zmizí z kontejneru typu.  
  
##  <a name="DisplayHiddenCompartmentsAndMemberrs"></a> Zobrazit skrytá přihrádky a členy typu  
  
1.  Otevřete a vyberte soubor diagramu tříd v Návrháři tříd.  
  
2.  Klikněte pravým tlačítkem na název typu se skrytým oddílem.  
  
3.  Klikněte na tlačítko **zobrazit všechny členy**.  
  
     Všechny skryté oddíly a členy se zobrazí v kontejneru typu.  
  
##  <a name="HideAssociationAndInheritance"></a> Skrýt relace  
  
1.  Otevřete a vyberte soubor diagramu tříd v Návrháři tříd.  
  
2.  Klikněte pravým tlačítkem myši na asociační čáru nebo čáru dědičnosti, kterou chcete skrýt.  
  
3.  Klikněte na tlačítko **skrýt** pro Asociační čáry a klikněte na **skrýt řádek dědičnosti** pro dědičnosti řádky.  
  
4.  Klikněte na tlačítko **zobrazit všechny členy**.  
  
     Všechny skryté oddíly a členy se zobrazí v kontejneru typu.  
  
##  <a name="DisplayAssociationAndInheritance"></a> Zobrazit skrytá relace  
  
1.  Otevřete a vyberte soubor diagramu tříd v Návrháři tříd.  
  
2.  Klikněte pravým tlačítkem na typ se skrytým přidružením nebo dědičností.  
  
 Klikněte na tlačítko **zobrazit všechny členy** pro Asociační čáry a klikněte na **zobrazit základní třída** nebo **Zobrazit odvozené třídy** pro dědičnosti řádky.  
  
##  <a name="RemoveCodeAndShape"></a> Odstranění obrazce z diagramu – třída  
Můžete odebrat tvar typu z diagramu tříd bez ovlivnění základního kódu typu. Odebrání tvarů typu z diagramu tříd ovlivní pouze tento diagram: základní kód definující typ a ostatní diagramy, které typ zobrazují, ovlivněny nejsou.  
  
1.  V diagramu tříd vyberte tvar typu, který chcete z diagramu odebrat.  
  
2.  Na **upravit** nabídce zvolte **odebrání Diagram**.  
  
     Tvar typu a čáry přidružení nebo dědičnosti spojené s tvarem se již v diagramu nezobrazí.  
  
##  <a name="DeleteTypeShapeAndCode"></a> Odstranit obrazce typu a jeho základní kódu  
  
1.  Klikněte pravým tlačítkem myši na tvar na návrhové ploše.  
  
2.  Vyberte **odstranit kód** v místní nabídce.  
  
     Tvar je odstraněn z diagramu a jeho základní kód je odstraněn z projektu.  
  
## <a name="see-also"></a>Viz také
[Práce s diagramy tříd](working-with-class-diagrams.md)   
[Postupy: změna mezi zápisem člena a zápisem asociace](how-to-change-between-member-notation-and-association-notation.md)   
[Postupy: zobrazení existujících typů](how-to-view-existing-types.md)   
[Zobrazování typů a vztahů](viewing-types-and-relationships.md)