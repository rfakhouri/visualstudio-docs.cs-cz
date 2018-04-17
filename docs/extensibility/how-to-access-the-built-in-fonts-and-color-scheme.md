---
title: 'Postupy: přístup k vestavěná písma a barevné schéma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- fonts, accessing built-in
- font and color control [Visual Studio SDK], categories
- colors, accessing built-in schemes
ms.assetid: 6905845e-e88e-4805-adcf-21da39108ec7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5f72640369152b03ef86383fda1162b1cfbacba8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-access-the-built-in-fonts-and-color-scheme"></a>Postupy: přístup k vestavěná písma a barevné schéma
Integrované vývojové prostředí (IDE) sady Visual Studio má schéma písma a barvy, která souvisí s okno editoru. Toto schéma prostřednictvím dostanete <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> rozhraní.

 Pokud chcete používat předdefinovaný písma a barvy schéma, VSPackage musí:

-   Zadejte kategorii, která pomocí výchozí služba písma a barev.

-   Zaregistrujte se na výchozí server písma a barev kategorii.

-   Poradit IDE konkrétní okno používá kategorií a předdefinovaných zobrazení položky pomocí <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer> a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer> rozhraní.

 Rozhraní IDE používá výsledné kategorie jako popisovač pro okno. Název kategorie se zobrazí v **zobrazit nastavení pro:** v rozevíracím seznamu **písma a barev** stránku vlastností.

### <a name="to-define-a-category-using-built-in-fonts-and-colors"></a>Chcete-li definovat kategorie pomocí předdefinovaných písma a barev

1.  Vytvořte libovolný identifikátor GUID.

     Tento identifikátor GUID slouží k jednoznačné identifikaci kategorii**.** Prostředí IDE výchozí písma a barvy specifikace opětovně používá tuto kategorii.

    > [!NOTE]
    >  Při načítání dat písma a barev pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorEvents> nebo dalších rozhraní VSPackages pomocí identifikátoru GUID předdefinované informace odkazovat.

2.  Název kategorie je přidat do tabulky řetězec v souboru prostředků (RC) VSPackage, tak, aby je možné lokalizovat podle potřeby, kdy se zobrazí v prostředí IDE.

     Další informace najdete v tématu [přidání nebo odstranění řetězce](/cpp/windows/adding-or-deleting-a-string).

### <a name="to-register-a-category-using-built-in-fonts-and-colors"></a>K registraci kategorii pomocí předdefinovaných písma a barev

1.  Vytvořte zvláštní druh položky registru kategorie v následujícím umístění:

     [HKLM\SOFTWARE\Microsoft \Visual Studio\\*\<verze sady Visual Studio >*\FontAndColors\\*\<kategorie >*]

     *\<Kategorie >* je Nelokalizováno název kategorie.

2.  Naplnění použít uložených písma a barevné schéma pro čtyři hodnoty v registru:

    |Název|Typ|Data|Popis|
    |----------|----------|----------|-----------------|
    |Kategorie|REG_SZ|GUID|Libovolný GUID, který identifikuje kategorii, která obsahuje uložených schéma písma a barvy.|
    |Balíček|REG_SZ|GUID|{F5E7E71D-1401-11D1-883B-0000F87579D2}<br /><br /> Tento identifikátor GUID je používán všechny VSPackages, které používají výchozí konfigurace písma a barvy.|
    |NameID|REG_DWORD|ID|ID prostředku názvu VSPackage do lokalizovatelný kategorie.|
    |ToolWindowPackage|REG_SZ|GUID|Identifikátor GUID VSPackage implementace <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> rozhraní.|

### <a name="to-initiate-the-use-of-system-provided-fonts-and-colors"></a>K zahájení používání poskytované systémem písma a barev

1.  Vytvoření instance <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer> rozhraní v rámci okna na implementaci a inicializace.

2.  Volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer.GetPropertyCategory%2A> metoda získat instanci <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer> rozhraní odpovídající aktuální <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> instance.

3.  Volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.SetProperty%2A> dvakrát.

    -   Volání s jednou `VSEDITPROPID_ViewGeneral_ColorCategory`jako argument.

    -   Volání s jednou `VSEDITPROPID_ViewGeneral_FontCategory` jako argument.

     Toto nastaví a zveřejňuje výchozí písma a barev služby jako vlastnost okna.

## <a name="example"></a>Příklad
 Následující příklad inicializuje použití vestavěná písma a barvy.

```cpp
CComVariant vt;
CComQIPtr<IVsTextEditorPropertyCategoryContainer> spPropCatContainer(m_spView);
if (spPropCatContainer != NULL){
    CComPtr<IVsTextEditorPropertyContainer> spPropContainer;
    if (SUCCEEDED(spPropCatContainer->GetPropertyCategory(GUID_EditPropCategory_View_MasterSettings,
                                                          &spPropContainer))){
        CComVariant vt;CComVariant VariantGUID(bstrGuidText);
        spPropContainer->SetProperty(VSEDITPROPID_ViewGeneral_FontCategory, VariantGUID);
        spPropContainer->SetProperty(VSEDITPROPID_ViewGeneral_ColorCategory, VariantGUID);
    }
}
```

## <a name="see-also"></a>Viz také

- [Pomocí písma a barev](../extensibility/using-fonts-and-colors.md)
- [Získávání písma a barev informace pro zabarvení textu](../extensibility/getting-font-and-color-information-for-text-colorization.md)
- [Přístup k uložené písma a barev](../extensibility/accessing-stored-font-and-color-settings.md)
- [Písma a barev – přehled](../extensibility/font-and-color-overview.md)