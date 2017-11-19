---
title: "Galerie privátní | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSIX galleries, private
- private galleries, VSIX
ms.assetid: b6b3dee7-91c5-4556-9f69-0d56b675e83b
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c58ce16489c02475a7d76327e9df19a6022109a4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="private-galleries"></a>Privátní Galerie
Ovládací prvky, šablony a nástroje, které vyvíjíte zveřejněním jim můžete sdílet *privátní Galerie* na intranetu pro vaši organizaci, následujícím způsobem:  
  
-   Vytvořte kanál Atom (RSS) do centrálního umístění vhodně nakonfigurované (úložiště) v síti intranet. Další informace najdete v tématu [postupy: vytvoření informačního kanálu Atom pro privátní Galerie](../extensibility/how-to-create-an-atom-feed-for-a-private-gallery.md).  
  
-   Distribuujte .pkgdef souboru, který popisuje privátní galerie. Doporučujeme tuto konfiguraci pro správce, kteří se chtějí připojit privátní Galerie na mnoho počítačů současně.  
  
## <a name="adding-a-private-gallery-to-extensions-and-updates-in-visual-studio"></a>Přidání privátní Galerie do rozšíření a aktualizace v sadě Visual Studio  
 Pokud privátní Galerie je k dispozici, můžete přidat jej do **rozšíření a aktualizace** v sadě Visual Studio.  
  
 ![Dialogové okno Přidání Správce rozšíření](../extensibility/media/em_adddialog.png "EM_AddDialog")  
  
#### <a name="to-add-a-private-gallery-to-extensions-and-updates"></a>Chcete-li přidat privátní Galerie rozšíření a aktualizace  
  
1.  Na řádku nabídek zvolte **nástroje**, **možnosti**.  
  
2.  V **prostředí** uzlu, vyberte **rozšíření a aktualizace**.  
  
3.  Vyberte **přidat** tlačítko.  
  
4.  V **název** pole, například zadejte název pro galerii privátní `My Gallery`.  
  
5.  V **URL** pole, zadejte adresu URL informačního kanálu Atom nebo web služby SharePoint, který je hostitelem privátního galerie.  
  
    1.  Pokud je hostitel informačního kanálu Atom která se připojuje k privátní galerie, adresa URL by vypadat tato: http://www.mywebsite/mygallery/atom.xml.  Tato adresa URL může odkazovat na soubor nebo síťovou cestu.  
  
    2.  Pokud se hostitel nachází Web služby SharePoint, adresa URL by vypadat tato: http://mysharepoint/sites/mygallery/forms/AllItems.aspx.  
  
### <a name="managing-private-galleries"></a>Správu galerií privátní  
 Správce můžete zpřístupnit privátní Galerie několik počítačů současně pomocí úpravy registru systému na každém počítači. K tomu, vytvořte soubor .pkgdef, který popisuje nových klíčů registru a jejich hodnoty.  Formát tohoto souboru je následující.  
  
```  
[$RootKey$\ExtensionManager\Repositories\{UniqueGUID}]  
@={URI}  (REG_SZ)  
Disabled=0 | 1 (DWORD)  
Priority=0 (highest priority) ... MaxInt (lowest priority) (DWORD) (uint)  
Protocol=Atom|Sharepoint (REG_SZ)  
DisplayName={DisplayName} (REG_SZ)  
DisplayNameResourceID={ID} (REG_SZ)  
DisplayNamePackageGuid={GUID} (REG_SZ)  
  
```  
  
 Další informace najdete v tématu [postupy: Správa privátní Galerie podle pomocí nastavení registru](../extensibility/how-to-manage-a-private-gallery-by-using-registry-settings.md).  
  
## <a name="installing-extensions-from-a-private-gallery"></a>Instalace rozšíření z Galerie privátní  
 Můžete vyhledat a nainstalovat rozšíření Visual Studia z privátní Galerie v **rozšíření a aktualizace**. Následující postup použijte privátní galerie s názvem `My Gallery`.  
  
 ![Správce rozšíření instalaci privátní Galerie](../extensibility/media/em_.png "EM_")  
  
#### <a name="to-search-for-and-install-extensions-from-a-private-gallery"></a>K vyhledání a instalace rozšíření z privátní Galerie  
  
1.  Na řádku nabídek zvolte **nástroje**, **rozšíření a aktualizace**.  
  
2.  V levém podokně vyberte **Online rozšíření**a potom vyberte **Moje galerie**.  
  
3.  V pravém podokně vyberte rozšíření a potom zvolte **Stáhnout** tlačítko.  
  
## <a name="updating-extensions-from-a-private-gallery"></a>Aktualizace rozšíření z Galerie privátní  
 Jak v galerii privátní jsou odeslány nové verze rozšíření sady Visual Studio, můžete aktualizovat rozšíření, které jste nainstalovali. Následující postup použijte privátní galerie s názvem `My Repository`.  
  
 ![Aktualizace Galerie rozšíření Manager privátní](../extensibility/media/em_update.png "EM_Update")  
  
#### <a name="to-update-an-installed-extension-from-a-private-gallery"></a>K aktualizaci nainstalovaného rozšíření z privátní Galerie  
  
1.  Na řádku nabídek zvolte **nástroje**, **rozšíření a aktualizace**.  
  
2.  V levém podokně vyberte **aktualizace**a potom vyberte **Moje úložiště**.  
  
3.  V pravém podokně vyberte rozšíření a potom zvolte **aktualizace** tlačítko.  
  
## <a name="see-also"></a>Viz také  
 [Hledání a používání rozšíření Visual Studia](../ide/finding-and-using-visual-studio-extensions.md)   
 [Přesouvání rozšíření Visual Studia](../extensibility/shipping-visual-studio-extensions.md)