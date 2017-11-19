---
title: "Prostředky v VSPackages | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managed VSPackages, resources in
- resources, managed VSPackages
- VSPackages, managed resources
ms.assetid: cc8c17a6-b190-4856-b001-0c1104f104b2
caps.latest.revision: "23"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e4f74912dc5233cd62a4d35465d34c70e376c1df
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="resources-in-vspackages"></a>Prostředky v VSPackages
Můžete vložit lokalizované prostředky v nativní satelitní knihovny DLL uživatelského rozhraní, spravované satelitní knihovny DLL, nebo ve spravovaných VSPackage sám sebe.  
  
 Některé prostředky, nemůže být vložen v VSPackages. Lze jej vkládat následující spravované typy:  
  
-   Řetězce  
  
-   Balíček zatížení klíče, (které jsou také řetězců)  
  
-   Nástroj okna ikony  
  
-   Zkompilované soubory příkaz tabulky výstup (c)  
  
-   Rastrové obrázky technického ředitele  
  
-   Nápověda příkazového řádku  
  
-   O dat dialogového okna  
  
 Prostředky v spravované balíčku jsou vybrané podle ID prostředku. Výjimkou je technického ředitele souboru, který musí mít název CTMENU. V tabulce prostředků jako musí být soubor technického ředitele `byte[]`. Všechny ostatní položky prostředků jsou identifikovány podle typu.  
  
 Můžete použít <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute> atribut a informuje [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] , spravované prostředky jsou k dispozici.  
  
 [!code-csharp[VSSDKResources#1](../../extensibility/internals/codesnippet/CSharp/resources-in-vspackages_1.cs)]
 [!code-vb[VSSDKResources#1](../../extensibility/internals/codesnippet/VisualBasic/resources-in-vspackages_1.vb)]  
  
 Nastavení <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute> tímto způsobem znamená, že [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] třeba ignorovat nespravované satelitní knihovny DLL při vyhledávání pro prostředky, například pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsShell.LoadPackageString%2A>. Pokud [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] zaznamená dva nebo více zdrojů, které mají stejné ID prostředku, použije na první prostředek najde.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu je spravovaný reprezentace ikonu okno nástroje.  
  
```  
<data name="1001"  
type="System.Resources.ResXFileRef,System.Windows.Forms">  
     <value>  
     MyToolWinIcon.bmp;  
     System.Drawing.Bitmap,  
     System.Drawing,  
     Version=1.0.0.0,  
     Culture=neutral,  
     PublicKeyToken=b03f5f7f11d50a3a  
     </value>  
</data>  
```  
  
 Následující příklad ukazuje, jak pro vložení technického ředitele bajtové pole, které musí mít název CTMENU.  
  
```  
<data name="CTMENU"  
type="System.Resources.ResXFileRef,System.Windows.Forms">  
     <value>  
     MyPackage.cto;  
     System.Byte[],  
     mscorlib,  
     Version=1.0.0.0,  
     Culture=neutral,  
     PublicKeyToken=b03f5f7f11d50a3a  
     </value>  
</data>  
```  
  
## <a name="implementation-notes"></a>Poznámky k implementaci  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]zpoždění načítání VSPackages kdykoli je to možné. Vložení soubor technického ředitele ve VSPackage důsledkem je, že [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] musí načíst všechny takové VSPackages v paměti během instalace, která je k sestavení sloučené příkaz tabulku. Prostředky lze extrahovat z VSPackage prověřením metadata bez spuštění kódu v VSPackage. V tuto chvíli není inicializován VSPackage, tak ztrátě výkonu je minimální.  
  
 Když [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] žádostí o prostředku z VSPackage po dokončení instalace, tento balíček je pravděpodobně již načten a inicializován, tak ztrátě výkonu je minimální.  
  
## <a name="see-also"></a>Viz také  
 [Správa VSPackages](../../extensibility/managing-vspackages.md)   
 [Místní zdroje v aplikacích MFC: satelitní knihovny DLL](/cpp/build/localized-resources-in-mfc-applications-satellite-dlls)   
