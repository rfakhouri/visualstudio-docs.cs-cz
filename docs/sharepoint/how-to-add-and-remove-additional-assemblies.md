---
title: 'Postupy: Přidání a odebrání dalších sestavení | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.RAD.CustomAssembly
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, packages
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: cadfffb2dbf977e23a0edb082065125aea4f5940
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-and-remove-additional-assemblies"></a>Postupy: Přidání a odebrání dalších sestavení
  Pokud balíček SharePoint závisí na jiných sestavení pro funkce nebo data, můžete přidat sestavení do vašeho řešení balíčku (WSP). Tímto způsobem, serveru SharePoint zajišťuje, že vlastní sestavení jsou nainstalovány s balíčkem.  
  
 Můžete také přidat a změnit bezpečné ovládací prvky a třída prostředků soubory přidružené k sestavení.  
  
## <a name="adding-additional-assemblies-safe-controls-and-class-resources"></a>Přidání dalších sestavení, bezpečné ovládací prvky a prostředky – třída  
 Můžete přidat další sestavení do balíčku řešení služby SharePoint. Další sestavení v řešení v izolovaném prostoru nasadit do globální mezipaměti sestavení, ale SharePoint – položky projektu v řešení v izolovaném prostoru jsou přidány do databáze s obsahem. Bezpečné ovládací prvky a třída prostředků můžete také přidat na tyto další sestavení. Další informace o bezpečné ovládací prvky najdete v tématu [poskytování balení a informace o nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md) nebo "Vytváření SafeControl – záznam" v [nasazení webové části v SharePoint Foundation](http://go.microsoft.com/fwlink/?LinkId=245505).  
  
#### <a name="to-add-an-existing-assembly"></a>Přidat existující sestavení  
  
1.  Otevřete **balíček Návrhář**. Další informace najdete v tématu [postupy: přizpůsobení balíčku řešení služby SharePoint](../sharepoint/how-to-customize-a-sharepoint-solution-package.md).  
  
2.  Vyberte **Upřesnit** kartě.  
  
3.  Vyberte **přidat** tlačítko a potom vyberte **přidat existující sestavení** ze seznamu.  
  
     **Přidat existující sestavení** zobrazí se dialogové okno.  
  
4.  Zvolte se třemi tečkami (![ASP.NET – Návrhář mobilních řešení elipsy](../sharepoint/media/mwellipsis.gif "ASP.NET – Návrhář mobilních řešení elipsy")) a potom vyberte sestavení, které chcete přidat. Doporučujeme použít relativní cestu k vybrané sestavení pro účely přenositelnost.  
  
5.  Pro **cíl nasazení**, vyberte **GlobalAssemblyCache** tlačítko nasadit sestavení do globální mezipaměti sestavení, nebo zvolte možnost **WebApplication** možnost tlačítko pro nasazení sestavení do složky webovou aplikaci na serveru, na kterém běží SharePoint.  
  
#### <a name="to-add-an-assembly-from-project-output"></a>Chcete-li přidat sestavení z výstupu projektu  
  
1.  Otevřete **balíček Návrhář**.  
  
     Další informace najdete v tématu [postupy: přizpůsobení balíčku řešení služby SharePoint](../sharepoint/how-to-customize-a-sharepoint-solution-package.md).  
  
2.  Vyberte **Upřesnit** kartě.  
  
3.  Vyberte **přidat** tlačítko a potom vyberte **přidat sestavení z výstupu projektu @** ze seznamu.  
  
     **Přidat sestavení z výstupu projektu @** zobrazí se dialogové okno.  
  
4.  V **zdroj projektu** seznam a vyberte zdroj projekt, který chcete přidat.  
  
5.  Pro **cíl nasazení**, vyberte **GlobalAssemblyCache** tlačítko nasadit sestavení do globální mezipaměti sestavení, nebo zvolte možnost **WebApplication** možnost tlačítko pro nasazení sestavení do složky webovou aplikaci na serveru, na kterém běží SharePoint.  
  
#### <a name="to-add-a-safe-control"></a>Přidání bezpečné ovládacího prvku  
  
1.  Otevřete **upravit existující sestavení** dialogové okno. K tomu, otevřete návrháře balíčků, zvolte **Upřesnit** kartě, zvolte sestavení a pak **upravit**tlačítko.  
  
2.  V **bezpečné ovládací prvky** podokně, vyberte **kliknutím sem přidejte novou položku** tlačítko.  
  
3.  V **název sestavení** sloupce, zadejte název sestavení.  
  
4.  V **Namespace** sloupce, zadejte název oboru názvů pro bezpečné ovládací prvek.  
  
5.  V **název typu** sloupce, zadejte název typu.  
  
#### <a name="to-add-a-class-resource"></a>Chcete-li přidat prostředek – třída  
  
1.  Otevřete **upravit existující sestavení** dialogové okno. K tomu, otevřete návrháře balíčků, zvolte **Upřesnit** kartě, zvolte sestavení a pak **upravit** tlačítko.  
  
2.  V **prostředky třídy** podokně, vyberte **kliknutím sem přidejte novou položku** tlačítko.  
  
3.  V **název souboru** sloupce, zvolte se třemi tečkami (![ASP.NET – Návrhář mobilních řešení elipsy](../sharepoint/media/mwellipsis.gif "ASP.NET – Návrhář mobilních řešení elipsy")) a vyberte třídu prostředek, který chcete přidat.  
  
## <a name="deleting-custom-assemblies"></a>Odstranění vlastní sestavení  
 Lze odstranit sestavení z balíčku služby SharePoint, nebo odstranit bezpečné ovládací prvky a prostředky třídy z existujících sestavení.  
  
#### <a name="to-delete-an-existing-assembly"></a>Chcete-li odstranit existující sestavení  
  
1.  Otevřete **balíček Návrhář**. Další informace najdete v tématu [postupy: přizpůsobení balíčku řešení služby SharePoint](../sharepoint/how-to-customize-a-sharepoint-solution-package.md).  
  
2.  Vyberte **Upřesnit** kartě.  
  
3.  V **dalších sestavení** podokně, vyberte vlastní sestavení, které chcete odstranit.  
  
4.  Vyberte **odstranit** tlačítko.  
  
#### <a name="to-delete-a-safe-control-for-an-assembly"></a>Chcete-li odstranit bezpečné ovládací prvek pro sestavení  
  
1.  Otevřete **upravit existující sestavení** dialogové okno. K tomu, otevřete návrháře balíčků, zvolte **Upřesnit** kartě, zvolte sestavení a pak **upravit** tlačítko.  
  
2.  Zvolte bezpečné ovládací prvek, který chcete odstranit.  
  
3.  Vyberte klíč odstranit.  
  
#### <a name="to-delete-a-class-resource-for-an-assembly"></a>Odstranit prostředek třídy pro sestavení  
  
1.  Otevřete **upravit existující sestavení** dialogové okno. K tomu, otevřete návrháře balíčků, zvolte **Upřesnit** kartě, zvolte sestavení a pak **upravit** tlačítko.  
  
2.  Vyberte třídu prostředek, který chcete odstranit.  
  
3.  Vyberte klíč odstranit.  
  
## <a name="see-also"></a>Viz také  
 [Vytváření funkcí služby SharePoint](../sharepoint/creating-sharepoint-features.md)   
 [Postupy: přizpůsobení funkce služby SharePoint](../sharepoint/how-to-customize-a-sharepoint-feature.md)   
 [Postupy: Přidání a odebrání položek z funkcí služby SharePoint](../sharepoint/how-to-add-and-remove-items-to-sharepoint-features.md)   
  
  