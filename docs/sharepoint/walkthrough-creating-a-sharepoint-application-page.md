---
title: 'Návod: Vytvoření stránky aplikace služby SharePoint | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- application pages [SharePoint development in Visual Studio], developing
- application pages [SharePoint development in Visual Studio], creating
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: e31b06d642947d88d1076b3ad365e62b663c8d4a
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120171"
---
# <a name="walkthrough-create-a-sharepoint-application-page"></a>Návod: Vytvoření stránky aplikace služby SharePoint
 
Stránky aplikace je specializovaná forma stránky ASP.NET. Stránky aplikací zahrnují obsah, který je sloučen s hlavní stránku služby SharePoint. Další informace najdete v tématu [vytvoření stránky aplikací pro službu SharePoint](../sharepoint/creating-application-pages-for-sharepoint.md).

Tento návod ukazuje postup vytvoření stránky aplikace a pak ho ladění pomocí místního webu služby SharePoint. Tato stránka zobrazuje všechny položky, které má každý uživatel vytvoření nebo úpravě ve všech lokalitách na serverové farmě.

Tento návod znázorňuje následující úlohy:

- Vytvoření projektu služby SharePoint.
- Přidání stránky aplikace do projektu služby SharePoint.
- Přidání ovládacích prvků ASP.NET na stránku aplikace.
- Přidání kódu na pozadí ovládacích prvků technologie ASP.NET.
- Testování stránky aplikace.

> [!NOTE]
> Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).

## <a name="prerequisites"></a>Požadavky

- Podporované edice systému Windows a služby SharePoint. Další informace najdete v tématu [požadavky na vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md).

## <a name="create-a-sharepoint-project"></a>Vytvoření projektu služby SharePoint

Nejprve vytvořte **prázdný projektu služby SharePoint**. Později, přidejte **stránky aplikace** položku do projektu.

1. Spustit [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].

2. Otevřete **nový projekt** dialogové okno, rozbalte seznam **Office/SharePoint** uzel v jazyce, který chcete použít a potom vyberte **řešení služby SharePoint** uzlu.

3. V **nainstalované šablony sady Visual Studio** podokně, vyberte **SharePoint 2010 - prázdný projekt** šablony. Název projektu **MySharePointProject**a potom zvolte **OK** tlačítko.

     **Průvodce vlastním nastavením SharePoint** se zobrazí. Tento průvodce umožňuje vyberte lokalitu, která budete používat k ladění projektu a úroveň důvěryhodnosti řešení.

4. Vyberte **nasadit jako řešení farmy** možnost tlačítko a potom vyberte **Dokončit** tlačítko přijmout výchozí místní web služby SharePoint.

## <a name="create-an-application-page"></a>Vytvoření stránky aplikace

K vytvoření stránky aplikace, přidejte **stránky aplikace** položku do projektu.

1. V **Průzkumníku řešení**, vyberte **MySharePointProject** projektu.

2. Na řádku nabídek zvolte **projektu** > **přidat novou položku**.

3. V **přidat novou položku** dialogovém okně vyberte **stránky aplikace (jenom řešení farmy** šablony.

4. Název stránky **SearchItems**a potom zvolte **přidat** tlačítko.

     Zobrazí stránka aplikace v návrháři Visual Web Developer **zdroj** zobrazení, kde se můžete podívat elementů HTML stránky. Návrhář zobrazí kód pro několik <xref:System.Web.UI.WebControls.Content> ovládací prvky. Každý ovládací prvek se mapuje <xref:System.Web.UI.WebControls.ContentPlaceHolder> ovládací prvek, který je definován v aplikaci stránku.

## <a name="design-the-layout-of-the-application-page"></a>Návrh rozložení stránky aplikace

Položka stránky aplikace umožňuje používat návrháře k přidávání ovládacích prvků ASP.NET na stránku aplikace. Tento návrhář je stejné návrháře použít v aplikaci Visual Web Developer. Přidání štítek, seznam přepínačů a tabulka, která se **zdroj** zobrazení v návrháři a nastavte vlastnosti stejně jako při návrhu všechny standardní stránky ASP.NET.

1. Na řádku nabídek zvolte **zobrazení** > **sada nástrojů**.

2. V uzlu standardní **sada nástrojů**, proveďte jednu z následujících kroků:

    - Otevřete místní nabídku pro **popisek** položku, vyberte **kopie**, otevřete místní nabídku pro řádek v části **PlaceHolderMain** obsahu ovládacího prvku v návrháři a potom Zvolte **vložení**.

    - Přetáhněte **popisek** položky z **sada nástrojů** na text **PlaceHolderMain** obsahu ovládacího prvku.

3. Opakujte předchozí krok pro přidání **rozevírací seznam** položky a **tabulky** položkou **PlaceHolderMain** obsahu ovládacího prvku.

4. V designeru, změňte hodnotu `Text` atribut ovládacího prvku popisek na **zobrazit všechny položky**.

5. V designeru, nahraďte `<asp:DropDownList>` element s následující kód XML.

    ```xml
    <asp:DropDownList ID="DropDownList1" runat="server" AutoPostBack="true"
     OnSelectedIndexChanged="DropDownList1_SelectedIndexChanged">
        <asp:ListItem Text="Created by me" Value="Author"></asp:ListItem>
        <asp:ListItem Text="Modified by me" Value="Editor"></asp:ListItem>
    </asp:DropDownList>
    ```

## <a name="handle-the-events-of-controls-on-the-page"></a>Zpracování událostí ovládacích prvků na stránce

Ovládací prvky v stránky aplikace zpracujte, stejně jako jakoukoli stránku ASP.NET. V tomto postupu bude zpracovávat `SelectedIndexChanged` události z rozevíracího seznamu.

1. Na **zobrazení** nabídce zvolte **kód**.

     Soubor kódu stránky aplikace se otevře v editoru kódu.

2. Přidejte následující metodu do `SearchItems` třídy. Tento kód zpracovává <xref:System.Web.UI.WebControls.ListControl.SelectedIndexChanged> události <xref:System.Web.UI.WebControls.DropDownList> voláním metody, která dále v tomto návodu vytvoříte.

     [!code-vb[SP_ApplicationPage#5](../sharepoint/codesnippet/VisualBasic/sp_applicationpage/layouts/sp_applicationpage/SearchItems.aspx.vb#5)]
     [!code-csharp[SP_ApplicationPage#5](../sharepoint/codesnippet/CSharp/sp_applicationpage/layouts/sp_applicationpage/SearchItems.aspx.cs#5)]

3. Přidejte následující příkazy na začátek souboru kódu stránky aplikace.

     [!code-vb[SP_ApplicationPage#1](../sharepoint/codesnippet/VisualBasic/sp_applicationpage/layouts/sp_applicationpage/SearchItems.aspx.vb#1)]
     [!code-csharp[SP_ApplicationPage#1](../sharepoint/codesnippet/CSharp/sp_applicationpage/layouts/sp_applicationpage/SearchItems.aspx.cs#1)]

4. Přidejte následující metodu do `SearchItems` třídy. Tato metoda provádí iteraci všechny weby na serverové farmě a hledá položky vytvořit nebo změnit podle aktuálního uživatele.

     [!code-vb[SP_ApplicationPage#2](../sharepoint/codesnippet/VisualBasic/sp_applicationpage/layouts/sp_applicationpage/SearchItems.aspx.vb#2)]
     [!code-csharp[SP_ApplicationPage#2](../sharepoint/codesnippet/CSharp/sp_applicationpage/layouts/sp_applicationpage/SearchItems.aspx.cs#2)]

5. Přidejte následující metodu do `SearchItems` třídy. Tato metoda zobrazí položky vytvořit nebo změnit aktuální uživatel v tabulce.

     [!code-vb[SP_ApplicationPage#3](../sharepoint/codesnippet/VisualBasic/sp_applicationpage/layouts/sp_applicationpage/SearchItems.aspx.vb#3)]
     [!code-csharp[SP_ApplicationPage#3](../sharepoint/codesnippet/CSharp/sp_applicationpage/layouts/sp_applicationpage/SearchItems.aspx.cs#3)]

## <a name="test-the-application-page"></a>Testovací stránka aplikace

Když spouštíte projekt, otevře se stránka serveru SharePoint a zobrazí se stránka aplikace.

1. V **Průzkumníku řešení**, otevřete místní nabídku pro stránku aplikace a zvolte **nastavit jako položku při spuštění**.

2. Vyberte **F5** klíč.

     Otevře se stránka serveru SharePoint.

3. Na stránce aplikace, vyberte **upraveném mi** možnost.

     Stránka aplikace aktualizuje a zobrazí všechny položky, které byly upraveny ve všech lokalitách na serverové farmě.

4. Na stránce aplikace zvolte **vytvořené mnou** v seznamu.

     Stránka aplikace aktualizuje a zobrazí všechny položky, které jste vytvořili ve všech lokalitách na serverové farmě.

## <a name="next-steps"></a>Další kroky

Další informace o stránek aplikací služby SharePoint, naleznete v části [vytvoření stránky aplikací pro službu SharePoint](../sharepoint/creating-application-pages-for-sharepoint.md).

Se více o tom, jak navrhnout obsahu stránce služby SharePoint pomocí návrháře Visual z těchto témat:

- [Vytvoření webové části pro službu SharePoint](../sharepoint/creating-web-parts-for-sharepoint.md).

- [Vytváření opakovaně použitelných ovládacích prvků pro webové části nebo stránky aplikací](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md).

## <a name="see-also"></a>Viz také:

[Postupy: vytvoření stránky aplikace](../sharepoint/how-to-create-an-application-page.md)  
[Napište _layouts aplikace](http://go.microsoft.com/fwlink/?LinkID=169274)
