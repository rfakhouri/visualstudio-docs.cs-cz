---
title: Prostředky v balíčcích VSPackage | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- managed VSPackages, resources in
- resources, managed VSPackages
- VSPackages, managed resources
ms.assetid: cc8c17a6-b190-4856-b001-0c1104f104b2
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3abcfebb7bbcc0eaa6a05760de4531f020b41ddb
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66318732"
---
# <a name="resources-in-vspackages"></a>Prostředky v balíčcích VSPackage
Lokalizované prostředky lze vložit v nativní satelitní knihovny DLL uživatelského rozhraní, spravovaných satelitních knihoven DLL, nebo ve spravované VSPackage samotný.

 Některé prostředky nemůže být vložený v balíčcích VSPackage. Následující spravované typy lze vložit:

- Řetězce

- Klíče načtení balíku sady (které jsou také řetězců)

- Ikony okno nástroje

- Zkompilované soubory výstupní tabulky příkaz (c)

- Rastrové obrázky technický ředitel

- Nápověda k příkazovému řádku

- O dat dialogového okna

  Prostředky v spravovaného balíčku jsou vybrány pomocí ID prostředku. Výjimka je soubor technický ředitel, který musí mít název CTMENU. Technologický ředitel souboru musí být uvedena v tabulce prostředků jako `byte[]`. Všechny ostatní položky prostředků se identifikují podle typu.

  Můžete použít <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute> atribut skutečnost [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] , spravované prostředky jsou k dispozici.

  [!code-csharp[VSSDKResources#1](../../extensibility/internals/codesnippet/CSharp/resources-in-vspackages_1.cs)]
  [!code-vb[VSSDKResources#1](../../extensibility/internals/codesnippet/VisualBasic/resources-in-vspackages_1.vb)]

  Nastavení <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute> tímto způsobem znamená, že [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ignorovat nespravované satelitní knihovny DLL při vyhledávání prostředků, například pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsShell.LoadPackageString%2A>. Pokud [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] zaznamená dva nebo více zdrojů, které mají stejné ID prostředku, použije první prostředek, které nalezne.

## <a name="example"></a>Příklad
 V následujícím příkladu je spravované reprezentace ikonu okna nástroje.

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

 Následující příklad ukazuje postup vložení technologický ředitel bajtové pole, které musí mít název CTMENU.

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
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] zpoždění načítání rozšíření VSPackages, kdykoli je to možné. Vložení souboru technologický ředitel v sadě VSPackage důsledkem je, že [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] musí načíst všechny takové rozšíření VSPackages paměti během instalace, což je při vytváření tabulky sloučené příkazů. Prostředky můžete extrahovat z VSPackage prozkoumáním metadata bez spuštění kódu v sady VSPackage. V tuto chvíli není inicializován sady VSPackage, tak ztrátě výkonu je minimální.

 Když [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] žádostí o prostředku z balíčku VSPackage po dokončení instalace, tento balíček je pravděpodobně již načten a inicializován, takže ke ztrátě výkonu je minimální.

## <a name="see-also"></a>Viz také
- [Správa rozšíření VSPackages](../../extensibility/managing-vspackages.md)
- [Lokalizované prostředky v aplikacích MFC: Satelitní knihovny DLL](/cpp/build/localized-resources-in-mfc-applications-satellite-dlls)
