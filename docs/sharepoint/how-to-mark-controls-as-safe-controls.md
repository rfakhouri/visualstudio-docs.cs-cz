---
title: 'Postupy: Označení ovládacích prvků jako bezpečných | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, safe controls
- SharePoint development in Visual Studio, advanced packaging tools
- safe controls [SharePoint development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: d3f0ff39658aca76318174143da52e17594ace24
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54875454"
---
# <a name="how-to-mark-controls-as-safe-controls"></a>Postupy: Označení ovládacích prvků jako bezpečných
  Pro zabezpečení SharePoint rozlišuje mezi webové ovládací prvky, které jsou chráněné proti injektáži skriptu a webové ovládací prvky, které nejsou. Ovládací prvky, chráněné nebo *bezpečné ovládací prvky*, je přístupný nedůvěryhodným uživatelům. Můžete označit ovládacích prvků jako bezpečných ve vlastnosti položky bezpečných ovládacích prvků položky Sharepointového projektu nebo v **návrháři balíčku** při přidávání sestavení do balíčku. Další informace naleznete v tématu  
  
 [soubor Web.config Změna nastavení](http://go.microsoft.com/fwlink/?LinkId=178965) a [registrace do webové části sestavení jako ovládací prvek bezpečný](http://go.microsoft.com/fwlink/?LinkId=171013).  
  
> [!IMPORTANT]  
>  Tyto postupy jsou pro ilustraci. Označení ovládacích prvků jako bezpečných pouze v případě, že jste si jisti, že jsou zabezpečené.  
  
## <a name="marking-safe-controls-in-the-safe-control-entries-property"></a>Označení bezpečné ovládací prvky ve vlastnosti položky bezpečného řízení  
  
#### <a name="to-mark-controls-as-safe-or-unsafe-in-the-safe-control-entries-property"></a>K označení ovládacích prvků jako bezpečných nebo nebezpečné ve vlastnosti položky bezpečného řízení
  
1.  Vytvoření řešení služby SharePoint pomocí projektu vizuální webové části.  
  
2.  Přidejte dva ovládací prvky webové části: textové pole a tlačítko. Ponechte názvy výchozích hodnotách TextBox1 a Button1, v uvedeném pořadí.  
  
3.  Přidat dvě položky do webové části **položky bezpečných ovládacích prvků** vlastnost. Chcete-li to provést, zvolte tři tečky (![elipsa ASP.NET – Návrhář mobilních řešení](../sharepoint/media/mwellipsis.gif "elipsa ASP.NET – Návrhář mobilních řešení")) vedle **položky bezpečných ovládacích prvků** vlastnost  **Vlastnosti** okna.  
  
     **Položky bezpečných ovládacích prvků** zobrazí se dialogové okno.  
  
4.  V **položky bezpečných ovládacích prvků** dialogového okna zvolte **přidat** dvakrát a přidejte dvě položky bezpečného řízení k **členy** podokně: jeden pro tlačítka a jeden pro textové pole.  
  
5.  Zvolte první položky bezpečného řízení a potom změňte hodnotu z jeho **bezpečné** vlastnost **False**, jeho **název typu** vlastnost **Button1**a jeho **bezpečné skriptu proti** vlastnost **False**.  
  
     Tento krok identifikuje ovládací prvek tlačítko jako ovládací prvek unsafe.  
  
6.  V seznamu vyberte druhou položku bezpečný ovládací prvek. Ponechte hodnotu jeho **bezpečné** vlastnost jako **True** a nastavte jeho **název typu** vlastnost **TextBox1** a jeho **bezpečné Proti skriptům** vlastnost **True**.  
  
     Ovládací prvek textové pole je nyní označena jako ovládací prvek, který je zabezpečený proti injektáži skriptu.  
  
7.  Zvolte **OK** tlačítka zavřete dialogové okno.  
  
## <a name="marking-safe-controls-in-the-package-designer"></a>Označení bezpečné ovládací prvky v Návrháři balíčku  
  
#### <a name="to-mark-controls-as-safe-or-unsafe-in-the-package-designer"></a>Označit ovládacích prvků jako bezpečných nebo nebezpečných v Návrháři balíčku
  
1.  Vytvoření řešení služby SharePoint pomocí projektu vizuální webové části.  
  
2.  Přidejte dva ovládací prvky webové části: textové pole a tlačítko. Ponechte názvy výchozích hodnotách TextBox1 a Button1, v uvedeném pořadí.  
  
     Poznamenejte si obor názvů ovládacího prvku vzhledem k tomu, že se později používá.  
  
3.  V panelu nabídky zvolte **sestavení** > **sestavit řešení** k sestavení projektu.  
  
4.  Vytvořte jiné řešení služby SharePoint.  
  
5.  V **Průzkumníka řešení**, otevřete místní nabídku *Package.Package* souboru a klikněte na tlačítko **otevřete** otevřete **návrháři balíčku**.  
  
6.  V **návrháři balíčku**, zvolte **Upřesnit** kartu.  
  
7.  V části **dodatečná sestavení**, zvolte **přidat** tlačítko a pak zvolte **přidat existující sestavení** ze seznamu.  
  
8.  V **přidat existující sestavení** dialogového okna zvolte tři tečky (![elipsa ASP.NET – Návrhář mobilních řešení](../sharepoint/media/mwellipsis.gif "elipsa ASP.NET – Návrhář mobilních řešení")) vedle  **Zdrojová cesta**.  
  
9. Vybrat sestavení z řešení SharePoint, kterou jste vytvořili v kroku 1 a klikněte na tlačítko **otevřít** tlačítko.  
  
10. V tomto příkladu ponechte **cíl nasazení** možnost GlobalAssemblyCache.  
  
     Tento krok způsobí, že sestavení pro nasazení do systému globální mezipaměti sestavení (GAC). Pokud chcete sestavení pro nasazení do webové aplikace (binární) složky, vyberte příslušnou možnost. Další informace najdete v tématu [nasazení webové části SharePoint Foundation](http://go.microsoft.com/fwlink/?LinkId=177509).  
  
11. V **bezpečné ovládací prvky** zvolte **kliknutím sem přidáte novou položku** tlačítko.  
  
12. Zadejte hodnoty pro vlastnosti v následující tabulce.  
  
    |Název vlastnosti|Hodnota|  
    |-------------------|-----------|  
    |Obor názvů|Plně kvalifikovaný obor názvů pro ovládací prvek, jako například **BdcModelProject1.VisualWebPart1**.|  
    |Název typu|Button1|  
    |Název sestavení|Na sestavení se silným názvem, jako: Microsoft.Office.SharePoint.ClientExtensions, Version=14.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c.|  
    |Bezpečné|Zrušte **bezpečné** zaškrtávací políčko.|  
    |Zabezpečeno proti skriptům|Nechte **bezpečné skriptu proti** zrušte zaškrtnutí políčka.|  
  
    > [!NOTE]  
    >  **Název sestavení** hodnotu pro sestavení pomocí přidat **Upřesnit** karty **návrháři balíčku** nemůže být token, musí být sestavení se silným názvem. Další informace najdete v tématu [vytvoření a použití sestavení](http://go.microsoft.com/fwlink/?LinkId=177513).  
  
13. Zvolte **kartu** klávesy vytvořte jinou položku bezpečný ovládací prvek.  
  
14. Zvolte **kliknutím sem přidáte novou položku** tlačítko znovu.  
  
15. Zadejte hodnoty pro vlastnosti v následující tabulce.  
  
    |Název vlastnosti|Hodnota|  
    |-------------------|-----------|  
    |Obor názvů|Plně kvalifikovaný obor názvů pro ovládací prvek, jako například **BdcModelProject1.VisualWebPart1**.|  
    |Název typu|TextBox1|  
    |Název sestavení|Na sestavení se silným názvem, jako: Microsoft.Office.SharePoint.ClientExtensions, Version=14.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c.|  
    |Bezpečné|Vyberte **bezpečné** zaškrtávací políčko.|  
    |Zabezpečeno proti skriptům|Vyberte **bezpečné skriptu proti** zaškrtávací políčko.|  
  
16. Zvolte **kartu** klíče a klikněte na tlačítko **OK** tlačítka zavřete dialogové okno.  
  
## <a name="see-also"></a>Viz také:
 [Zadání informací o balení a nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)   
 [Balení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
