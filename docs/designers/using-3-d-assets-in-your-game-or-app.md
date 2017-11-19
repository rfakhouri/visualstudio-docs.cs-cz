---
title: "Pomocí 3D prostředky v hry nebo aplikace | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.ImageContentTask.ContentOutput
- VC.Project.MeshContentTask.ContentOutput
- VC.Project.ImageContentTask.GeneratePremultipliedAlpha
- VC.Project.ImageContentTask.Compress
- VC.Project.ShaderGraphContentTask.ContentOutput
- VC.Project.ImageContentTask.GenerateMips
ms.assetid: ea587909-e434-46a8-abf8-9b3e95a58b4f
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 5613790632c4bd462c1efbb3f218a0299b276179
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="using-3-d-assets-in-your-game-or-app"></a>Používání 3D prostředků ve hře nebo aplikaci
Tento článek popisuje, jak můžete použít [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ke zpracování 3D prostředky a zahrnout je ve vašich sestaveních.  
  
 Po použití nástrojů v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] vytvořit 3D prostředky, dalším krokem je jejich použití ve vaší aplikaci. Ale před použitím je, vaše prostředky musí být uvedeny ve formátu, který můžete porozumět DirectX. Při transformaci vaše prostředky [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] poskytuje sestavení vlastní nastavení pro jednotlivé typy asset, který může vytvořit. Zahrnout prostředky buildu, všechny, které musíte udělat, je nakonfigurujete svůj projekt použijte vlastní nastavení sestavení, přidat prostředky do projektu a nakonfigurovat prostředky používat vlastní nastavení správná sestavení. Potom můžete načíst prostředky do vaší aplikace a použít je pomocí vytvoření a naplnění DirectX prostředky stejně jako v jakékoli jiné DirectX aplikaci.  
  
## <a name="configuring-your-project"></a>Konfigurace projektu  
 Před nasazením vaše 3D prostředky jako součást sestavení, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] se chcete dozvědět o typech prostředků, které chcete nasadit. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]již ví o mnoho běžné typy souborů, ale protože pouze určité typy aplikací, použijte 3D prostředky [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] není předpokládá, že projektu budete stavět tyto typy souborů. Se dá zjistit [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] , vaše aplikace používá tyto typy prostředků pomocí *přizpůsobení sestavení*– soubory, které informují [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] postupy zpracování různých typů souborů užitečným způsobem – které jsou k dispozici pro každý typ prostředku. Protože tato přizpůsobení budou použita na jednotlivých projektů, je všechny, které musíte udělat, do projektu přidejte příslušné úpravy.  
  
#### <a name="to-add-the-build-customizations-to-your-project"></a>Chcete-li přidat přizpůsobením sestavení do projektu  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídky projektu a zvolte **sestavení závislosti**, **sestavení přizpůsobení**. **Souborů Visual C++ sestavení přizpůsobení** se zobrazí dialogové okno.  
  
2.  V části **k dispozici soubory sestavení přizpůsobení**, zaškrtněte políčka, které odpovídají asset typy, které chcete použít v projektu, jak je popsáno v této tabulce:  
  
    |Typ prostředku|Přizpůsobení název sestavení|  
    |----------------|------------------------------|  
    |Textury a obrázků|**ImageContentTask (.targets, props)**|  
    |3D modely|**MeshContentTask (.targets, props)**|  
    |Shadery|**ShaderGraphContentTask (.targets, props)**|  
  
3.  Vyberte **OK** tlačítko.  
  
## <a name="including-assets-in-your-build"></a>Včetně prostředky v buildu  
 Teď, když projektu ví o různých druhů 3D prostředky, které chcete použít, dalším krokem je určit, které soubory jsou 3D prostředky a jaké druhy prostředky jsou.  
  
#### <a name="to-add-an-asset-to-your-build"></a>Přidat prostředek do vaší sestavení  
  
1.  V **Průzkumníku řešení**ve vašem projektu, otevřete v místní nabídce prostředek a zvolte **vlastnosti**. Assetu **stránka vlastností** se zobrazí dialogové okno.  
  
2.  Ujistěte se, že **konfigurace** a **platformy** vlastnosti jsou nastaveny na hodnoty, které chcete změny použít.  
  
3.  V části **vlastnosti konfigurace**, zvolte **Obecné**a poté v mřížku vlastností v rámci **Obecné**, nastavte **typ položky** vlastnost Typ položky odpovídající obsahu kanálu. Například vyberte soubor obrazu nebo texture **bitové kopie obsahu kanálu**.  
  
    > [!IMPORTANT]
    >  Ve výchozím nastavení [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] předpokládá, že různé druhy soubory obrázků by měl být zařazené do kategorie pomocí **Image** typ, který je součástí položky [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Proto je nutné změnit **typ položky** vlastnost každé bitové kopie, kterou chcete zpracovat kanálu obsahu bitové kopie. Jiné typy obsahu kanálu zdrojové soubory pro 3D modely a výchozí grafiky visual shaderu na správnou **typ položky**.  
  
4.  Vyberte **OK** tlačítko.  
  
 Tady jsou tři typy položek obsahu kanálu a jejich přidružené zdroje a výstup typy souborů.  
  
|Typ položky|Typy souborů zdroje|Výstupní formát souboru|  
|---------------|-----------------------|------------------------|  
|**Bitové kopie obsahu kanálu**|Portable Network Graphics (.png)<br /><br /> JPEG (JPG, JPEG, JPE, JFIF)<br /><br /> Přímé prostor pro kreslení (.dds)<br /><br /> Graphics Interchange Format (.gif)<br /><br /> Rastrový obrázek (BMP, DIB)<br /><br /> Tagged Image File Format (.tif, .tiff)<br /><br /> Targa (TGA)|Nastavení obnovovací prostor (.dds)|  
|**Obsahu kanálu oka**|Soubor výměnu AutoDesk FBX (.fbx)<br /><br /> Soubor DAE standardu Collada (.dae)<br /><br /> OBJ společnosti Wavefront souboru (.obj)|Soubor 3D mřížky (.cmo)|  
|**Shaderu obsahu kanálu**|Graf Visual shaderu (.dgsl)|Výstup kompilované shaderu (.cso)|  
  
## <a name="configuring-asset-content-pipeline-properties"></a>Konfigurace vlastností asset obsahu kanálu  
 Vlastnosti kanálu obsahu jednotlivých souborů asset můžete nastavit tak, aby ho budou vytvořeny v určitým způsobem.  
  
#### <a name="to-configure-content-pipeline-properties"></a>Konfigurace vlastností obsahu kanálu  
  
1.  V **Průzkumníku řešení**ve vašem projektu otevřete místní nabídku pro souboru prostředku a potom zvolte **vlastnosti**. Assetu **stránka vlastností** se zobrazí dialogové okno.  
  
2.  Ujistěte se, že **konfigurace** a **platformy** vlastnosti jsou nastaveny na hodnoty, které chcete změny použít.  
  
3.  V části **vlastnosti konfigurace**, vyberte uzel obsahu kanálu – například **bitové kopie obsahu kanálu** pro prostředky texture a bitové kopie – a potom v mřížce vlastnost, nastavte vlastnosti na odpovídající hodnoty. Například pokud chcete vygenerovat mipmaps pro prostředek texture v čase vytvoření buildu, nastavte **generovat Mips** vlastnost **Ano**.  
  
4.  Vyberte **OK** tlačítko.  
  
### <a name="image-content-pipeline-configuration"></a>Konfigurace obsahu kanálu bitové kopie  
 Při použití nástroje obsahu kanálu bitovou kopii k sestavení texture asset, můžete komprimovat texture různými způsoby, uvádí, zda by měl být vygenerován v čase vytvoření buildu MIP úrovně a změňte název souboru výstupního souboru.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|**Komprimovat**|Určuje typ komprese, který se používá pro výstupní soubor.<br /><br /> Jsou dostupné možnosti:<br /><br /> -   **Bez komprese**<br />-   **Komprese BC1_UNORM**<br />-   **Komprese BC1_UNORM_SRGB**<br />-   **Komprese BC2_UNORM**<br />-   **Komprese BC2_UNORM_SRGB**<br />-   **Komprese BC3_UNORM**<br />-   **Komprese BC3_UNORM_SRGB**<br />-   **Komprese BC4_UNORM**<br />-   **Komprese BC4_SNORM**<br />-   **Komprese BC5_UNORM**<br />-   **Komprese BC5_SNORM**<br />-   **Komprese BC6H_UF16**<br />-   **Komprese BC6H_SF16**<br />-   **Komprese BC7_UNORM**<br />-   **Komprese BC7_UNORM_SRGB**<br /><br /> Informace, o které komprese formátů podporovaných v různých verzích rozhraní DirectX najdete v tématu [Průvodce programováním pro DXGI](http://go.microsoft.com/fwlink/p/?LinkId=246265).|  
|Převést na formát předem vynásobená alfa|**Ano** převést bitovou kopii na předem vynásobená alfa formátu ve výstupním souboru; jinak **ne**. Pouze výstupního souboru se změní, Zdrojová bitová kopie je beze změny.|  
|**Generovat Mips**|**Ano** generovat řetěz úplné MIP v čase vytvoření buildu a její zahrnutí do výstupního souboru; jinak **ne**. Pokud **ne**a zdrojový soubor již obsahuje řetězec mipmap, pak výstupní soubor bude mít řetěz MIP; jinak hodnota výstupní soubor bude mít žádné MIP řetězu.|  
|**Výstup obsahu**|Určuje název souboru výstupního souboru. **Důležité:** změna příponu názvu souboru výstupního souboru, nemá žádný vliv na jeho formátu.|  
  
### <a name="mesh-content-pipeline-configuration"></a>Konfigurace obsahu kanálu oka  
 Když použijete nástroj obsahu kanálu oka k sestavení asset mřížky, můžete změnit název výstupního souboru.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|**Výstup obsahu**|Určuje název souboru výstupního souboru. **Důležité:** změna příponu názvu souboru výstupního souboru, nemá žádný vliv na jeho formátu.|  
  
### <a name="shader-content-pipeline-configuration"></a>Konfigurace obsahu kanálu shaderu  
 Když použijete nástroj obsahu kanálu shaderu k sestavení shaderu asset, můžete změnit název výstupního souboru.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|**Výstup obsahu**|Určuje název souboru výstupního souboru. **Důležité:** změna příponu názvu souboru výstupního souboru, nemá žádný vliv na jeho formátu.|  
  
## <a name="loading-and-using-3-d-assets-at-run-time"></a>Načtení a použití 3D prostředky v době běhu  
  
### <a name="using-textures-and-images"></a>Použití textury a obrázků  
 Direct3D – poskytuje funkce pro vytváření texture prostředků. Knihovna nástrojů D3DX11 v Direct3D – 11 poskytuje další funkce pro vytváření prostředků texture a zobrazení zdrojů přímo z soubory obrázků. Další informace o tom, jak vytvořit prostředek texture v Direct3D – 11 najdete v tématu [textury](http://go.microsoft.com/fwlink/p/?LinkID=246267). Další informace o tom, jak vytvořit texture prostředku nebo zobrazení prostředků v knihovně D3DX11 ze souboru bitové kopie najdete v části [postupy: Inicializace Texture z soubor](http://go.microsoft.com/fwlink/p/?LinkId=246268).  
  
### <a name="using-3-d-models"></a>Použití 3D modelů  
 Direct3D – 11 neposkytuje funkce pro vytváření prostředků z 3D modelů. Místo toho budete muset psát kód, který načte soubor 3D modelu a vytvoří vrchol a index vyrovnávací paměti, které představují 3D modelu a všechny prostředky, které vyžaduje modelu – například textury nebo shadery.  
  
### <a name="using-shaders"></a>Pomocí shadery  
 Direct3D – poskytuje funkce pro vytváření shaderu prostředků a jejich vazby kanálu programovatelný grafiky. Další informace o tom, jak vytvořit prostředek shaderu v Direct3D – a navázat jej do kanálu najdete v tématu [Průvodce programováním pro HLSL](http://go.microsoft.com/fwlink/p/?LinkID=261521).  
  
 V kanálu programovatelný grafiky musí každá fáze v kanálu dát do další fáze kanálu výsledku, který je naformátovaný způsobem, který můžete porozumět. Protože návrháře shaderu lze vytvořit pouze shadery pixelů, to znamená, že je na své aplikace a zajistěte, aby byla data, která obdrží formát, který se očekává, že. Několik fází programovatelný shaderu předcházet shaderu pixelů a provádění transformací geometrickou – shaderu vrchol, shaderu trupu, shaderu domény a shaderu geometrie. Fáze-programovatelný teselace také předchází shaderu pixelů. Bez ohledu na to, které z těchto fází přímo předchází shaderu pixelů se musí dát svůj výsledek v tomto formátu:  
  
```hlsl  
  
struct PixelShaderInput  
{  
    float4 pos : SV_POSITION;  
    float4 diffuse : COLOR;  
    float2 uv : TEXCOORD0;  
    float3 worldNorm : TEXCOORD1;  
    float3 worldPos : TEXCOORD2;  
    float3 toEye : TEXCOORD3;  
    float4 tangent : TEXCOORD4;  
    float3 normal : TEXCOORD5;  
};  
```  
  
 V závislosti na shaderu Návrhář uzly, které používáte ve vaší shaderu budete také muset poskytnout dodatečná data ve formátu podle tyto definice:  
  
```  
  
Texture2D Texture1 : register( t0 );  
Texture2D Texture2 : register( t1 );  
Texture2D Texture3 : register( t2 );  
Texture2D Texture4 : register( t3 );  
Texture2D Texture5 : register( t4 );  
Texture2D Texture6 : register( t5 );  
Texture2D Texture7 : register( t6 );  
Texture2D Texture8 : register( t7 );  
  
TextureCube CubeTexture1 : register( t8 );  
TextureCube CubeTexture2 : register( t9 );  
TextureCube CubeTexture3 : register( t10 );  
TextureCube CubeTexture4 : register( t11 );  
TextureCube CubeTexture5 : register( t12 );  
TextureCube CubeTexture6 : register( t13 );  
TextureCube CubeTexture7 : register( t14 );  
TextureCube CubeTexture8 : register( t15 );  
  
SamplerState TexSampler : register( s0 );  
  
cbuffer MaterialVars : register (b0)  
{  
    float4 MaterialAmbient;  
    float4 MaterialDiffuse;  
    float4 MaterialSpecular;  
    float4 MaterialEmissive;  
    float MaterialSpecularPower;  
};  
  
cbuffer LightVars : register (b1)  
{  
    float4 AmbientLight;  
    float4 LightColor[4];  
    float4 LightAttenuation[4];  
    float3 LightDirection[4];  
    float LightSpecularIntensity[4];  
    uint IsPointLight[4];  
    uint ActiveLights;  
}  
  
cbuffer ObjectVars : register(b2)  
{  
    float4x4 LocalToWorld4x4;  
    float4x4 LocalToProjected4x4;  
    float4x4 WorldToLocal4x4;  
    float4x4 WorldToView4x4;  
    float4x4 UVTransform4x4;  
    float3 EyePosition;  
};  
  
cbuffer MiscVars : register(b3)  
{  
    float ViewportWidth;  
    float ViewportHeight;  
    float Time;  
};  
```  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Postupy: Export Texture, který obsahuje Mipmaps](../designers/how-to-export-a-texture-that-contains-mipmaps.md)|Popisuje, jak exportovat texture, který obsahuje předpočítané mipmaps pomocí bitové kopie obsahu kanálu.|  
|[Postupy: Export Texture, který má předem vynásobený Alpha](../designers/how-to-export-a-texture-that-has-premultiplied-alpha.md)|Popisuje, jak použít bitovou kopii obsahu kanálu pro exportování texture, který obsahuje předem vynásobí alfanumerické hodnoty.|  
|[Postupy: Export texturou pro použití s Direct2D nebo Javascipt aplikace](../designers/how-to-export-a-texture-for-use-with-direct2d-or-javascipt-apps.md)|Popisuje, jak použít bitovou kopii obsahu kanálu pro exportování texture, které je možné v aplikaci Direct2D nebo JavaScript.|  
|[Práce s 3D prostředky pro hry a aplikace](../designers/working-with-3-d-assets-for-games-and-apps.md)|Popisuje nástroje pro úpravy, které poskytuje Visual Studio pro vytváření a manipulace s nimi 3D prostředky, které zahrnují textury a bitové kopie, 3D modely a shadery.|  
|[Postupy: Export shaderu](../designers/how-to-export-a-shader.md)|Popisuje, jak exportovat shaderu z Návrháře shaderu.|