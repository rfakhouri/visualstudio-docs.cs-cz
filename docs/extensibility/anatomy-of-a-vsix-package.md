---
title: Anatomie balíčku VSIX | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- visual studio extension
- vsix
- packages
ms.assetid: 8b86d62f-c274-4e91-82e0-38cdb9a423d5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d811c1539dde655657331b7ca3511bbd4e80063f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31099548"
---
# <a name="anatomy-of-a-vsix-package"></a>Anatomie balíčku VSIX
Balíčku VSIX je soubor VSIX, který obsahuje jeden nebo více rozšíření Visual Studia, spolu s metadaty, které Visual Studio využívá ke klasifikaci a instalaci rozšíření. Aby metadata jsou obsaženy v manifestu VSIX a souboru .xml [Content_Types]. Balíčku VSIX může také obsahovat jeden nebo více souborů Extension.vsixlangpack zajistit lokalizované instalace text a může obsahovat další balíčků VSIX pro instalaci závislosti.  
  
 Formát balíčku VSIX dodržuje standard otevřete balení konvence OPC (). Balíček obsahuje binární soubory a podpůrné soubory, společně s soubor XML [Content_Types] a VSIX soubor manifestu. Jeden balíček VSIX může obsahovat výstup více projektů nebo i více balíčků, které mají své vlastní manifest.  
  
> [!NOTE]
>  Názvy soubory obsažené ve VSIX balíčky nesmí obsahovat mezery ani znaky, které jsou vyhrazené v identifikátory URI (Uniform Resource), jako je definován v rámci [ \[RFC2396\]](http://go.microsoft.com/fwlink/?LinkId=90339).  
  
## <a name="the-vsix-manifest"></a>VSIX Manifest  
 VSIX manifest obsahuje informace o rozšíření nainstalovat a postupuje podle pravidel VSX Schema. Další informace najdete v tématu [VSIX rozšíření schématu 1.0 odkaz](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b). Manifest VSIX příklad najdete v části [PackageManifest Element (kořenový Element, VSX Schema)](http://msdn.microsoft.com/en-us/f8ae42ba-775a-4d2b-976a-f556e147f187).  
  
 Musí mít název manifestu VSIX `extension.vsixmanifest` když je součástí soubor VSIX.  
  
## <a name="the-content"></a>Obsah  
 Balíčku VSIX může obsahovat šablony, položek sady nástrojů, VSPackages nebo jakýkoli jiný druh rozšíření, která je podporována sadou Visual Studio.  
  
## <a name="language-packs"></a>Jazykové sady  
 Balíčku VSIX může obsahovat jednou nebo více souborů Extension.vsixlangpack zajistit textu během instalace. Další informace najdete v tématu [lokalizace balíčky VSIX](../extensibility/localizing-vsix-packages.md).  
  
## <a name="dependencies-and-references"></a>Závislosti a odkazy  
 Balíčku VSIX může obsahovat jiné balíčky VSIX jako odkazy. Každý z těchto dalších balíčků musí obsahovat vlastní VSIX manifestu.  
  
 Pokud se uživatel pokusí o instalaci rozšíření, které se má závislosti, instalační program ověří, že požadovaná sestavení jsou nainstalované na uživatele systému. Pokud nejsou nalezeny požadovaná sestavení, **rozšíření a aktualizace** zobrazí seznam chybí sestavení.  
  
 Pokud manifest rozšíření zahrnuje jednu nebo více [odkaz](http://msdn.microsoft.com/en-us/32c52934-e81e-4b53-8cb6-4df45ef7bfa8) elementů **rozšíření a aktualizace** porovná manifest každý odkaz na rozšíření, které jsou nainstalované v systému a nainstaluje odkazované rozšíření, pokud již není nainstalována. Pokud je nainstalovaná starší verze odkazované rozšíření, nahradí novější verze ho.  
  
 Pokud na projekt v řešení vícenásobného projektu obsahuje odkaz na jiný projekt ve stejném řešení, zahrnuje balíčku VSIX závislosti tohoto projektu. Toto chování můžete přepsat pomocí kliknutím na odkaz pro interní projekt a potom v **vlastnosti** okně Nastavení **výstup skupiny součástí VSIX** vlastnost `BuiltProjectOutputGroup`.  
  
 Pokud chcete satelitní knihovny DLL z odkazovaná sestavení v balíčku VSIX, přidejte `SatelliteDllsProjectOutputGroup` k **výstup skupiny součástí VSIX** vlastnost.  
  
## <a name="installation-location"></a>Umístění instalace  
 Během instalace **rozšíření a aktualizace** hledá obsah balíčku VSIX ve složce % LocalAppData%\Microsoft\VisualStudio\14.0\Extensions.  
  
 Ve výchozím nastavení instalace se týká pouze aktuálního uživatele, protože % LocalAppData % je adresář konkrétního uživatele. Ale pokud nastavíte [AllUsers](http://msdn.microsoft.com/en-us/ac817f50-3276-4ddb-b467-8bbb1432455b) element manifestu, aby `True`, rozšíření se nainstalují v části... \\ *VisualStudioInstallationFolder*\Common7\IDE\Extensions a bude k dispozici pro všechny uživatele počítače.  
  
## <a name="contenttypesxml"></a>[Content_Types] .xml  
 Soubor .xml [Content_Types] Určuje typy souborů v souboru rozšířené VSIX. Visual Studio použije tento soubor při instalaci balíčku, ale nenainstaluje samotném souboru. Další informace o tento soubor najdete v tématu [The struktura .xml [Content_types] souboru](the-structure-of-the-content-types-dot-xml-file.md).  
  
 Soubor XML [Content_Types] je nutný pomocí otevřete balení konvence (OPC) standardní. Další informace o OPC najdete v tématu [OPC: A nová standardní pro balení vaše Data](http://go.microsoft.com/fwlink/?LinkID=148207) na webu MSDN.