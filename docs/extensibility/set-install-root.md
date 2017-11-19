---
title: "Instalace mimo složku rozšíření s VSIX v3 | Microsoft Docs"
ms.custom: 
ms.date: 11/09/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 913c3745-8aa9-4260-886e-a05aecfb2225
caps.latest.revision: "1"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1b604a70c44b6fd25888ee5419efbb95f95a0a4a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="installing-outside-the-extensions-folder"></a>Instalace mimo složku rozšíření

Od verze Visual Studio 2017 a VSIX v3 (verze 3), se teď podporují instalaci rozšíření prostředky mimo složku rozšíření. V současné době jsou jako platný instalační umístění (kde [INSTALLDIR] je namapovaný na instanci aplikace Visual Studio Instalační adresář) povolené následující umístění:

* \MSBuild [INSTALLDIR]
* \Xml\Schemas [INSTALLDIR]
* \Common7\IDE\PublicAssemblies [INSTALLDIR]
* \Licenses [INSTALLDIR]
* \Common7\IDE\ReferenceAssemblies [INSTALLDIR]
* \Common7\IDE\RemoteDebugger [INSTALLDIR]
* \Common7\IDE\VC\VCTargets [INSTALLDIR]

>**Poznámka:** formát VSIX neumožňuje k instalaci mimo struktura složek instalaci VS.

Chcete-li podporují instalaci na tyto adresáře, musí být VSIX nainstalovanou "jednotlivých instancí na počítač". To může být povolena zaškrtnutím políčka "všechna users" v Návrháři extension.vsixmanifest:

![Zkontrolujte všechny uživatele](media/check-all-users.png)

## <a name="how-to-set-the-installroot"></a>Jak nastavit Kořenová_složka_instalace

Pokud chcete nastavit instalační adresáře, můžete použít **vlastnosti** oken v sadě Visual Studio. Například můžete nastavit `InstallRoot` vlastnost odkaz na projekt do jednoho z výše uvedených umístění:

![Vlastnosti kořenové instalace](media/install-root-properties.png)

Některá metadata se přidá do odpovídajících `ProjectReference` vlastnost uvnitř souboru .csproj VSIX projektu:

```xml
 <ProjectReference Include="..\ClassLibrary1\ClassLibrary1.csproj">
        <Project>{69a979f1-eba2-43e7-9346-0e56e803508b}</Project>
        <Name>ClassLibrary1</Name>
        <InstallRoot>PublicAssemblies</InstallRoot>
 </ProjectReference>
```

>**Poznámka:** můžete upravit souboru .csproj přímo, pokud dáváte přednost.

## <a name="how-to-set-a-subpath-under-the-installroot"></a>Postup nastavení v části Kořenová_složka_instalace dílčí cestou k

Pokud chcete nainstalovat dílčí cestu pod `InstallRoot`, můžete tak učinit nastavením `VsixSubPath` vlastnost stejně jako `InstallRoot` vlastnost. Předpokládejme, chceme, aby naše projektu odkaz výstup pro instalaci ' [INSTALLDIR]\MSBuild\MyCompany\MySDK\1.0'. Jsme to můžete provést snadno pomocí návrháře vlastnost:

![dílčí sada cestu](media/set-subpath.png)

Odpovídající změny .csproj bude vypadat takto:

```xml
<ProjectReference Include="..\ClassLibrary1\ClassLibrary1.csproj">
       <Project>{69a979f1-eba2-43e7-9346-0e56e803508b}</Project>
       <Name>ClassLibrary1</Name>
       <InstallRoot>MSBuild</InstallRoot>
       <VSIXSubPath>MyCompany\MySDK\1.0</VSIXSubPath>
</ProjectReference>
```

## <a name="extra-information"></a>Další informace

Změny vlastností návrháře platí pro více než jen odkazů projektu; můžete nastavit `InstallRoot` metadata pro položky v rámci projektu také (pomocí stejné metody popsané výše).
