---
title: 'Postupy: Lokalizace značek ASPX | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- localizing XML [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, localizing
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 433111855aab18bea412e5774cfe7a2fca2b2a7b
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56609823"
---
# <a name="how-to-localize-aspx-markup"></a>Postupy: Lokalizace značek ASPX
  [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] stránky (.aspx) obvykle používají pevně zakódované řetězcové hodnoty. Chcete-li lokalizovat tyto řetězce, je nahraďte výrazy, které odkazují na lokalizované prostředky.

## <a name="localize-aspx-markup"></a>Lokalizace značek ASPX

#### <a name="to-localize-aspx-markup"></a>Lokalizace značek ASPX

1.  Přidání souborů prostředků: jeden pro výchozí jazyk a jeden pro každý lokalizovaný jazyk.

     Pokud lokalizujete pouze značek a kódu není, přidejte položku projektu globální soubor prostředků. Pokud lokalizujete kódu a kódu, přidejte položku projektu souboru prostředků.

    1.  Chcete-li přidat globální soubor prostředků v **Průzkumníka řešení**, otevřete místní nabídku pro položku Sharepointového projektu a klikněte na tlačítko **přidat** > **nová položka**. V části služby SharePoint **2010** uzlu, vyberte **globální soubor prostředků** šablony.

    2.  Chcete-li přidat soubor prostředků v **Průzkumníka řešení**, otevřete místní nabídku pro položku Sharepointového projektu a klikněte na tlačítko **přidat** > **nová položka**. V části **jazyka Visual Basic** nebo **Visual C#**  uzlu, vyberte **soubor prostředků** šablony.

    > [!NOTE]
    >  Ujistěte se, že přidání souborů prostředků do položky projektu služby SharePoint, který povolí vlastnost typ nasazení. Tato vlastnost je vyžadováno později v tomto postupu. Pokud vaše řešení nemá žádné položky projektu služby SharePoint, můžete přidat prázdný projekt SharePoint a odeberte výchozí *Elements.xml* souboru.

2.  Pojmenujte soubor prostředků výchozího jazyka jméno dle vašeho výběru s *RESX* rozšíření, například MyAppResources.resx. Použijte stejný základní název pro každý lokalizovaný soubor prostředků, ale přidat jazykovou verzi [!INCLUDE[TLA2#tla_id](../sharepoint/includes/tla2sharptla-id-md.md)]. Například pojmenujte německý lokalizovaný prostředek *MyAppResources.de-DE.resx*.

3.  Změňte hodnotu **typ nasazení** vlastnosti každého souboru prostředků na **AppGlobalResource** způsobit pro nasazení do složky App_GlobalResources serveru.

4.  Pokud používáte prostředky k lokalizaci kódu kromě značek ASPX, ponechte hodnotu **akce sestavení** jednotlivých souborů jako **integrovaný prostředek**. Pokud používáte pouze k lokalizaci značky soubory prostředků, můžete volitelně změnit hodnotu vlastnosti soubory, které chcete **obsahu**. Další informace najdete v tématu [řešení služby SharePoint lokalizovat](../sharepoint/localizing-sharepoint-solutions.md).

5.  Otevřete každý soubor prostředků a přidejte lokalizované řetězce, pomocí stejná ID řetězce do každého souboru.

6.  V [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] značky stránky ASPX a ovládací prvek, nahraďte pevně zakódované řetězce s hodnotami, které používají následující formát:

    ```aspx-csharp
    <%$Resources:Resource File Name, String ID%>
    ```

     Například chcete-li lokalizovat text pro ovládací prvek popisek na stránku aplikace, změníte:

    ```aspx-csharp
    <asp:Content ID="Main" ContentPlaceHolderID="PlaceHolderMain" runat="server">
    <asp:Label ID="lbl" runat="server" Text="Label text"></asp:Label>
    </asp:Content>
    ```

     až

    ```aspx-csharp
    <asp:Content ID="Main" ContentPlaceHolderID="PlaceHolderMain" runat="server">
    <asp:Label ID="lbl" runat="server" Text="<%$Resources:MyAppResources,String1%>"></asp:Label>
    </asp:Content>
    ```

7.  Zvolte **F5** klíče pro sestavení a spuštění aplikace.

8.  Ve službě SharePoint změňte jazyk zobrazení z výchozího.

     Lokalizované řetězce jsou zobrazeny v aplikaci. Chcete-li zobrazit lokalizované prostředky, musí mít SharePoint server nainstalovanou jazykovou sadu odpovídající jazykové verzi souboru prostředků.

## <a name="see-also"></a>Viz také:
- [Lokalizace řešení služby SharePoint](../sharepoint/localizing-sharepoint-solutions.md)
- [Postupy: Lokalizace funkce](../sharepoint/how-to-localize-a-feature.md)
- [Postupy: Přidejte soubor prostředků](../sharepoint/how-to-add-a-resource-file.md)
- [Postupy: Lokalizace kódu](../sharepoint/how-to-localize-code.md)
