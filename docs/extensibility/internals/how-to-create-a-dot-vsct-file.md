---
title: 'Postupy: Vytvořte. Soubor vsct | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- VSCT files, creating
ms.assetid: b955f51c-f9f9-49c3-a8e4-63b6eb0e0341
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c3155ff69db461e652b11ff6e8ec6d405000244f
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68924173"
---
# <a name="how-to-create-a-vsct-file"></a>Postupy: Vytvoření souboru. vsct

Existuje několik způsobů, jak vytvořit soubor konfigurace příkazového řádku sady Visual Studio založený na jazyce XML ( *. vsct*).

- V [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] šabloně balíčku můžete vytvořit nový VSPackage.

- K vygenerování souboru z existujícího souboru *. ctc* můžete použít konfigurační tabulku *vsct. exe*založenou na jazyce XML.

- Pomocí *vsct. exe* můžete vygenerovat soubor *. vsct* z existujícího souboru *. technický ředitel* .

- Můžete ručně vytvořit nový soubor *. vsct* .

  Tento článek vysvětluje, jak ručně vytvořit nový soubor *. vsct* .

### <a name="to-manually-create-a-new-vsct-file"></a>Ruční vytvoření nového souboru. vsct

1. Spustit [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

2. Na **souboru** nabídky, přejděte k **nový**a potom klikněte na tlačítko **souboru**.

3. V podokně **šablony** klikněte na **soubor XML** a potom klikněte na **otevřít**.

4. V nabídce **zobrazení** klikněte na **vlastnosti** . zobrazí se vlastnosti souboru XML.

5. V okně **vlastnosti** klikněte na tlačítko **Procházet** na vlastnosti **schémata** .

6. V seznamu schémat XSD vyberte schéma *vsct. xsd* . Pokud není v seznamu, klikněte na tlačítko **Přidat** a vyhledejte soubor na místním disku. Až skončíte, klikněte na **OK** .

7. V souboru XML zadejte *< příkazového řádku* a potom stiskněte klávesu **TAB**. Uzavřete značku zadáním *>* .

    Tato akce vytvoří základní soubor *. vsct* .

8. Vyplňte prvky souboru XML, který chcete přidat, podle [odkazu schématu vsct XML](../../extensibility/vsct-xml-schema-reference.md). Další informace najdete v tématu [vytváření souborů. vsct](../../extensibility/internals/authoring-dot-vsct-files.md).

<a name="how-to-create-a-dot-vsct-file-from-an-existing-dot-ctc-file"></a>

## <a name="how-to-create-a-vsct-file-from-an-existing-ctc-file"></a>Postupy: Vytvoření souboru. vsct z existujícího souboru. ctc

Soubor *. vsct* založený na jazyce XML můžete vytvořit z existující tabulky příkazů *. ctc* zdrojového souboru. Díky tomu můžete využít nové formáty kompilátoru příkazového řádku založeného na [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] jazyce XML (vsct).

### <a name="to-create-a-vsct-file-from-a-ctc-file"></a>Vytvoření souboru. vsct ze souboru. ctc

1. Získá kopii jazyka Perl.

2. Získejte kopii skriptu Perl *ConvertCTCToVSCT.pl*, která se obvykle nachází v  *\<instalační cestě sady Visual Studio SDK > složce \VisualStudioIntegration\Tools\bin* .

3. Získejte kopii zdrojového souboru *. ctc* , který chcete převést.

4. Soubory umístěte do stejného adresáře.

5. V okně [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] příkazového řádku přejděte do adresáře.

6. type

   ```
   perl.exe ConvertCTCtoVSCT.pl PkgCmd.ctc PkgCmd.vsct
   ```

    kde *PkgCmd. ctc* je název souboru *. ctc* a *PkgCmd. vsct* je název souboru *. vsct* , který chcete vytvořit.

    Tato akce vytvoří nový zdrojový soubor tabulky příkazů XML *. vsct* . Soubor můžete zkompilovat pomocí *vsct. exe*, kompilátoru VSCT, stejně jako jakýkoli jiný soubor *. vsct* .

   > [!NOTE]
   > Můžete zlepšit čitelnost souboru *. vsct* přeformátováním komentářů XML.

<a name="how-to-create-a-dot-vsct-file-from-an-existing-dot-cto-file"></a>

## <a name="how-to-create-a-vsct-file-from-an-existing-cto-file"></a>Postupy: Vytvoření souboru. vsct z existujícího souboru. technický ředitel

Soubor *. vsct* založený na jazyce XML můžete vytvořit z existujícího binárního souboru *. technický ředitel* . Díky tomu je možné využít nové formáty kompilátoru příkazových tabulek. Tento proces funguje i v případě, že soubor *. technický ředitel* byl zkompilován ze souboru *. ctc* . Soubor *. vsct* můžete upravit a zkompilovat do jiného souboru. technický ředitel.

### <a name="to-create-a-vsct-file-from-a-cto-file"></a>Vytvoření souboru. vsct ze souboru. technický ředitel

1. Získejte kopie souboru *. technický ředitel* a odpovídajícího souboru *. ctsym* .

2. Soubory umístěte do stejného adresáře jako kompilátor *vsct. exe* .

3. V příkazovém řádku sady Visual Studio přejdete do adresáře, který obsahuje soubory *. technický ředitel* a *. ctsym* .

4. type

    ```
    vsct.exe <ctofilename>.cto <vsctfilename>.vsct -S<symfilename>.ctsym
    ```

     kde \<ctofilename\> \<\> \< je název souboru. technický ředitel, vsctfilename je název souboru. vsct, který chcete vytvořit, a symfilename je název\> soubor *. ctsym* .

     Tento proces vytvoří nový soubor kompilátoru tabulky příkazů XML *. vsct* . Soubor můžete upravit a zkompilovat pomocí *vsct. exe*, kompilátoru VSCT, stejně jako jakýkoli jiný soubor *. vsct* .

## <a name="compile-the-code"></a>Kompilace kódu
 Pouhým přidáním souboru *. vsct* do projektu nezpůsobí jeho zkompilování. Je nutné jej začlenit do procesu sestavení.

### <a name="to-add-a-vsct-file-to-project-compilation"></a>Přidání souboru. vsct do kompilace projektu

1. Otevřete soubor projektu v editoru. Pokud je projekt načten, je nutné jej nejprve uvolnit.

2. Přidejte [element Item](../../msbuild/itemgroup-element-msbuild.md) , který obsahuje `VSCTCompile` element, jak je znázorněno v následujícím příkladu.

    ```xml
    <ItemGroup>
      <VSCTCompile Include="TopLevelMenu.vsct">
        <ResourceName>Menus.ctmenu</ResourceName>
      </VSCTCompile>
    </ItemGroup>

    ```

     Element by měl být vždy nastaven na `Menus.ctmenu`hodnotu. `ResourceName`

3. Pokud projekt obsahuje soubor *. resx* , přidejte `EmbeddedResource` `MergeWithCTO` element, který obsahuje element, jak je znázorněno v následujícím příkladu:

    ```xml
    <EmbeddedResource Include="VSPackage.resx">
      <MergeWithCTO>true</MergeWithCTO>
      <ManifestResourceName>VSPackage</ManifestResourceName>
    </EmbeddedResource>

    ```

     Tento kód by měl jít uvnitř `ItemGroup` elementu, který obsahuje vložené prostředky.

4. Otevřete soubor balíčku, obvykle nazvaný  *\<\>ProjectName Package.cs* nebo  *\<ProjectName\>Package. vb*, v editoru.

5. `ProvideMenuResource` Přidejte atribut do třídy Package, jak je znázorněno v následujícím příkladu.

    ```csharp
    [ProvideMenuResource("Menus.ctmenu", 1)]
    ```

     První hodnota parametru se musí shodovat s hodnotou `ResourceName` atributu, který jste definovali v souboru projektu.

## <a name="see-also"></a>Viz také:
- [Soubory Author. vsct](../../extensibility/internals/authoring-dot-vsct-files.md)
- [Soubory tabulek příkazů sady Visual Studio (. vsct)](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
- [Referenční dokumentace schématu VSCT XML](../../extensibility/vsct-xml-schema-reference.md)