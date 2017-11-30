---
title: "XML Öğesi Değişmez Değeri (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlLiteralElement
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
caps.latest.revision: "32"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: de5825a6af1dd1b93c3c85651125cf817dc564f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="xml-element-literal-visual-basic"></a><span data-ttu-id="db8f0-102">XML Öğesi Değişmez Değeri (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="db8f0-102">XML Element Literal (Visual Basic)</span></span>

<span data-ttu-id="db8f0-103">Temsil eden bir hazır değer bir <xref:System.Xml.Linq.XElement> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="db8f0-103">A literal that represents an <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db8f0-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="db8f0-104">Syntax</span></span>  
  
```xml  
<name [ attributeList ] />  
-or-  
<name [ attributeList ] > [ elementContents ] </[ name ]>  
```  
  
## <a name="parts"></a><span data-ttu-id="db8f0-105">Bölümler</span><span class="sxs-lookup"><span data-stu-id="db8f0-105">Parts</span></span>  
  
-   `<`  
  
     <span data-ttu-id="db8f0-106">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="db8f0-106">Required.</span></span> <span data-ttu-id="db8f0-107">Başlangıç öğesi etiketi açar.</span><span class="sxs-lookup"><span data-stu-id="db8f0-107">Opens the starting element tag.</span></span>  
  
-   `name`  
  
     <span data-ttu-id="db8f0-108">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="db8f0-108">Required.</span></span> <span data-ttu-id="db8f0-109">Öğesinin adı.</span><span class="sxs-lookup"><span data-stu-id="db8f0-109">Name of the element.</span></span> <span data-ttu-id="db8f0-110">Aşağıdakilerden birini biçimdedir:</span><span class="sxs-lookup"><span data-stu-id="db8f0-110">The format is one of the following:</span></span>  
  
    -   <span data-ttu-id="db8f0-111">Düz metin biçiminde öğe adı için `[ePrefix:]eName`, burada:</span><span class="sxs-lookup"><span data-stu-id="db8f0-111">Literal text for the element name, of the form `[ePrefix:]eName`, where:</span></span>  
  
        |<span data-ttu-id="db8f0-112">Bölümü</span><span class="sxs-lookup"><span data-stu-id="db8f0-112">Part</span></span>|<span data-ttu-id="db8f0-113">Açıklama</span><span class="sxs-lookup"><span data-stu-id="db8f0-113">Description</span></span>|  
        |---|---|  
        |`ePrefix`|<span data-ttu-id="db8f0-114">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="db8f0-114">Optional.</span></span> <span data-ttu-id="db8f0-115">Öğesi için XML ad alanı öneki.</span><span class="sxs-lookup"><span data-stu-id="db8f0-115">XML namespace prefix for the element.</span></span> <span data-ttu-id="db8f0-116">İle tanımlanmış genel bir XML ad alanı olmalıdır bir `Imports` dosyası veya proje düzeyinde veya bu öğe veya bir üst öğesi tanımlanmış yerel bir XML ad alanı bildirimi.</span><span class="sxs-lookup"><span data-stu-id="db8f0-116">Must be a global XML namespace that is defined with an `Imports` statement in the file or at the project level, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`eName`|<span data-ttu-id="db8f0-117">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="db8f0-117">Required.</span></span> <span data-ttu-id="db8f0-118">Öğesinin adı.</span><span class="sxs-lookup"><span data-stu-id="db8f0-118">Name of the element.</span></span> <span data-ttu-id="db8f0-119">Aşağıdakilerden birini biçimdedir:</span><span class="sxs-lookup"><span data-stu-id="db8f0-119">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="db8f0-120">-Düz metin.</span><span class="sxs-lookup"><span data-stu-id="db8f0-120">-   Literal text.</span></span> <span data-ttu-id="db8f0-121">Bkz: [bildirilmiş XML öğeleri ve özniteliklerinin adları](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="db8f0-121">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="db8f0-122">-Biçiminde ifade katıştırılmış `<%= eNameExp %>`.</span><span class="sxs-lookup"><span data-stu-id="db8f0-122">-   Embedded expression of the form `<%= eNameExp %>`.</span></span> <span data-ttu-id="db8f0-123">Türü `eNameExp` olmalıdır `String` ya da örtük olarak parametresinin türü <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="db8f0-123">The type of `eNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
  
    -   <span data-ttu-id="db8f0-124">İfade biçiminde katıştırılmış `<%= nameExp %>`.</span><span class="sxs-lookup"><span data-stu-id="db8f0-124">Embedded expression of the form `<%= nameExp %>`.</span></span> <span data-ttu-id="db8f0-125">Türü `nameExp` olmalıdır `String` ya da örtük olarak dönüştürülebilir türü <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="db8f0-125">The type of `nameExp` must be `String` or a type implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="db8f0-126">Katıştırılmış bir ifade, bir öğenin kapatma etiketi içinde izin verilmiyor.</span><span class="sxs-lookup"><span data-stu-id="db8f0-126">An embedded expression is not allowed in a closing tag of an element.</span></span>  
  
-   `attributeList`  
  
     <span data-ttu-id="db8f0-127">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="db8f0-127">Optional.</span></span> <span data-ttu-id="db8f0-128">Öznitelikler listesi literal bildirildi.</span><span class="sxs-lookup"><span data-stu-id="db8f0-128">List of attributes declared in the literal.</span></span>  
  
     `attribute [ attribute ... ]`  
  
     <span data-ttu-id="db8f0-129">Her `attribute` aşağıdaki sözdizimi biri:</span><span class="sxs-lookup"><span data-stu-id="db8f0-129">Each `attribute` has one of the following syntaxes:</span></span>  
  
    -   <span data-ttu-id="db8f0-130">Özniteliği formun atama `[aPrefix:]aName=aValue`, burada:</span><span class="sxs-lookup"><span data-stu-id="db8f0-130">Attribute assignment, of the form `[aPrefix:]aName=aValue`, where:</span></span>  
  
        |<span data-ttu-id="db8f0-131">Bölümü</span><span class="sxs-lookup"><span data-stu-id="db8f0-131">Part</span></span>|<span data-ttu-id="db8f0-132">Açıklama</span><span class="sxs-lookup"><span data-stu-id="db8f0-132">Description</span></span>|  
        |---|---|  
        |`aPrefix`|<span data-ttu-id="db8f0-133">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="db8f0-133">Optional.</span></span> <span data-ttu-id="db8f0-134">Öznitelik için XML ad alanı öneki.</span><span class="sxs-lookup"><span data-stu-id="db8f0-134">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="db8f0-135">İle tanımlanmış genel bir XML ad alanı olmalıdır bir `Imports` deyimi veya bu öğe veya bir üst öğesi tanımlanmış yerel bir XML ad alanı.</span><span class="sxs-lookup"><span data-stu-id="db8f0-135">Must be a global XML namespace that is defined with an `Imports` statement, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`aName`|<span data-ttu-id="db8f0-136">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="db8f0-136">Required.</span></span> <span data-ttu-id="db8f0-137">Özniteliğin adı.</span><span class="sxs-lookup"><span data-stu-id="db8f0-137">Name of the attribute.</span></span> <span data-ttu-id="db8f0-138">Aşağıdakilerden birini biçimdedir:</span><span class="sxs-lookup"><span data-stu-id="db8f0-138">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="db8f0-139">-Düz metin.</span><span class="sxs-lookup"><span data-stu-id="db8f0-139">-   Literal text.</span></span> <span data-ttu-id="db8f0-140">Bkz: [bildirilmiş XML öğeleri ve özniteliklerinin adları](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="db8f0-140">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="db8f0-141">-Biçiminde ifade katıştırılmış `<%= aNameExp %>`.</span><span class="sxs-lookup"><span data-stu-id="db8f0-141">-   Embedded expression of the form `<%= aNameExp %>`.</span></span> <span data-ttu-id="db8f0-142">Türü `aNameExp` olmalıdır `String` ya da örtük olarak parametresinin türü <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="db8f0-142">The type of `aNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
        |`aValue`|<span data-ttu-id="db8f0-143">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="db8f0-143">Optional.</span></span> <span data-ttu-id="db8f0-144">Öznitelik değeri.</span><span class="sxs-lookup"><span data-stu-id="db8f0-144">Value of the attribute.</span></span> <span data-ttu-id="db8f0-145">Aşağıdakilerden birini biçimdedir:</span><span class="sxs-lookup"><span data-stu-id="db8f0-145">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="db8f0-146">-Tırnak işaretleri içine değişmez değer metin.</span><span class="sxs-lookup"><span data-stu-id="db8f0-146">-   Literal text, enclosed in quotation marks.</span></span><br /><span data-ttu-id="db8f0-147">-Biçiminde ifade katıştırılmış `<%= aValueExp %>`.</span><span class="sxs-lookup"><span data-stu-id="db8f0-147">-   Embedded expression of the form `<%= aValueExp %>`.</span></span> <span data-ttu-id="db8f0-148">Herhangi bir tür izin verilir.</span><span class="sxs-lookup"><span data-stu-id="db8f0-148">Any type is allowed.</span></span>|  
  
    -   <span data-ttu-id="db8f0-149">İfade biçiminde katıştırılmış `<%= aExp %>`.</span><span class="sxs-lookup"><span data-stu-id="db8f0-149">Embedded expression of the form `<%= aExp %>`.</span></span>  
  
-   `/>`  
  
     <span data-ttu-id="db8f0-150">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="db8f0-150">Optional.</span></span> <span data-ttu-id="db8f0-151">Öğenin içerik olmadan boş bir öğe olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="db8f0-151">Indicates that the element is an empty element, without content.</span></span>  
  
-   `>`  
  
     <span data-ttu-id="db8f0-152">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="db8f0-152">Required.</span></span> <span data-ttu-id="db8f0-153">Başlangıç ya da boş öğe etiketi sona erer.</span><span class="sxs-lookup"><span data-stu-id="db8f0-153">Ends the beginning or empty element tag.</span></span>  
  
-   `elementContents`  
  
     <span data-ttu-id="db8f0-154">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="db8f0-154">Optional.</span></span> <span data-ttu-id="db8f0-155">Öğesinin içeriği.</span><span class="sxs-lookup"><span data-stu-id="db8f0-155">Content of the element.</span></span>  
  
     `content [ content ... ]`  
  
     <span data-ttu-id="db8f0-156">Her `content` şunlardan biri olabilir:</span><span class="sxs-lookup"><span data-stu-id="db8f0-156">Each `content` can be one of the following:</span></span>  
  
    -   <span data-ttu-id="db8f0-157">Düz metin.</span><span class="sxs-lookup"><span data-stu-id="db8f0-157">Literal text.</span></span> <span data-ttu-id="db8f0-158">İçindeki tüm boşluk `elementContents` herhangi bir metin ise önemli hale gelir.</span><span class="sxs-lookup"><span data-stu-id="db8f0-158">All the white space in `elementContents` becomes significant if there is any literal text.</span></span>  
  
    -   <span data-ttu-id="db8f0-159">İfade biçiminde katıştırılmış `<%= contentExp %>`.</span><span class="sxs-lookup"><span data-stu-id="db8f0-159">Embedded expression of the form `<%= contentExp %>`.</span></span>  
  
    -   <span data-ttu-id="db8f0-160">XML öğesi değişmez değeri.</span><span class="sxs-lookup"><span data-stu-id="db8f0-160">XML element literal.</span></span>  
  
    -   <span data-ttu-id="db8f0-161">XML açıklama değişmez değeri.</span><span class="sxs-lookup"><span data-stu-id="db8f0-161">XML comment literal.</span></span> <span data-ttu-id="db8f0-162">Bkz: [XML açıklama değişmez değeri](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="db8f0-162">See [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>  
  
    -   <span data-ttu-id="db8f0-163">XML işleme talimatı değişmez.</span><span class="sxs-lookup"><span data-stu-id="db8f0-163">XML processing instruction literal.</span></span> <span data-ttu-id="db8f0-164">Bkz: [XML işleme talimatı değişmez değeri](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="db8f0-164">See [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span>  
  
    -   <span data-ttu-id="db8f0-165">XML CDATA değişmez.</span><span class="sxs-lookup"><span data-stu-id="db8f0-165">XML CDATA literal.</span></span> <span data-ttu-id="db8f0-166">Bkz: [XML CDATA değişmez değeri](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span><span class="sxs-lookup"><span data-stu-id="db8f0-166">See [XML CDATA Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span></span>  
  
-   `</[name]>`  
  
     <span data-ttu-id="db8f0-167">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="db8f0-167">Optional.</span></span> <span data-ttu-id="db8f0-168">Öğesi için kapanış etiketi temsil eder.</span><span class="sxs-lookup"><span data-stu-id="db8f0-168">Represents the closing tag for the element.</span></span> <span data-ttu-id="db8f0-169">İsteğe bağlı `name` parametresi katıştırılmış ifade sonucu olduğunda kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="db8f0-169">The optional `name` parameter is not allowed when it is the result of an embedded expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="db8f0-170">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="db8f0-170">Return Value</span></span>  
 <span data-ttu-id="db8f0-171">Bir <xref:System.Xml.Linq.XElement> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="db8f0-171">An <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db8f0-172">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="db8f0-172">Remarks</span></span>  
 <span data-ttu-id="db8f0-173">XML öğesi değişmez değer sözdizimi oluşturmak için kullanabileceğiniz <xref:System.Xml.Linq.XElement> kodunuzda nesneleri.</span><span class="sxs-lookup"><span data-stu-id="db8f0-173">You can use the XML element literal syntax to create <xref:System.Xml.Linq.XElement> objects in your code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db8f0-174">XML değişmez değer, satır devamlılığı karakterleri kullanmadan birden fazla satır yayılabilir.</span><span class="sxs-lookup"><span data-stu-id="db8f0-174">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="db8f0-175">Bu özellik, bir XML belgesinden içeriği Kopyala ve doğrudan yapıştırın sağlar bir [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.</span><span class="sxs-lookup"><span data-stu-id="db8f0-175">This feature enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.</span></span>  
  
 <span data-ttu-id="db8f0-176">Formun ifadelerin katıştırılmış `<%= exp %>` , bir XML öğesi değişmez değer dinamik bilgi eklemenize olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="db8f0-176">Embedded expressions of the form `<%= exp %>` enable you to add dynamic information to an XML element literal.</span></span> <span data-ttu-id="db8f0-177">Daha fazla bilgi için bkz: [XML'de katıştırılmış ifadeler](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="db8f0-177">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="db8f0-178">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Derleyici çağrıları XML öğesi değişmez değeri dönüştürür <xref:System.Xml.Linq.XElement.%23ctor%2A> oluşturucusu ve gerekliyse, <xref:System.Xml.Linq.XAttribute.%23ctor%2A> Oluşturucusu.</span><span class="sxs-lookup"><span data-stu-id="db8f0-178">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler converts the XML element literal into calls to the <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor and, if it is required, the <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="db8f0-179">XML ad alanları</span><span class="sxs-lookup"><span data-stu-id="db8f0-179">XML Namespaces</span></span>  
 <span data-ttu-id="db8f0-180">XML ad alanı önekleri kodda birçok kez aynı ad alanından öğeler ile XML değişmez değerleri oluşturmanız gerektiğinde faydalıdır.</span><span class="sxs-lookup"><span data-stu-id="db8f0-180">XML namespace prefixes are useful when you have to create XML literals with elements from the same namespace many times in code.</span></span> <span data-ttu-id="db8f0-181">Kullanarak tanımlayan genel XML ad alanı önekleri kullanabilirsiniz `Imports` deyimi veya kullanarak tanımladığınız yerel önekleri `xmlns:xmlPrefix="xmlNamespace"` öznitelik sözdizimi.</span><span class="sxs-lookup"><span data-stu-id="db8f0-181">You can use global XML namespace prefixes, which you define by using the `Imports` statement, or local prefixes, which you define by using the `xmlns:xmlPrefix="xmlNamespace"` attribute syntax.</span></span> <span data-ttu-id="db8f0-182">Daha fazla bilgi için bkz: [Imports deyimi (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="db8f0-182">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
 <span data-ttu-id="db8f0-183">XML ad alanları için kapsam kurallarına uygun olarak yerel önekleri genel önekler'ne göre önceliğe sahiptir.</span><span class="sxs-lookup"><span data-stu-id="db8f0-183">In accordance with the scoping rules for XML namespaces, local prefixes take precedence over global prefixes.</span></span> <span data-ttu-id="db8f0-184">XML değişmez değeri bir XML ad alanı tanımlıyorsa, ancak bu ad alanı katıştırılmış bir ifadede görünür ifadeleri kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="db8f0-184">However, if an XML literal defines an XML namespace, that namespace is not available to expressions that appear in an embedded expression.</span></span> <span data-ttu-id="db8f0-185">Katıştırılmış ifade yalnızca genel XML ad alanı erişebilir.</span><span class="sxs-lookup"><span data-stu-id="db8f0-185">The embedded expression can access only the global XML namespace.</span></span>  
  
 <span data-ttu-id="db8f0-186">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Derleyici bir XML değişmez değer oluşturulan kodun bir yerel ad tanımında içine kullanılan her genel XML ad alanı dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="db8f0-186">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler converts each global XML namespace that is used by an XML literal into a one local namespace definition in the generated code.</span></span> <span data-ttu-id="db8f0-187">Kullanılmayan genel XML ad alanları oluşturulan kodda görünmez.</span><span class="sxs-lookup"><span data-stu-id="db8f0-187">Global XML namespaces that are not used do not appear in the generated code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db8f0-188">Örnek</span><span class="sxs-lookup"><span data-stu-id="db8f0-188">Example</span></span>  
 <span data-ttu-id="db8f0-189">Aşağıdaki örnekte, iki iç içe geçmiş boş öğeye sahip basit bir XML öğesi oluşturulacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="db8f0-189">The following example shows how to create a simple XML element that has two nested empty elements.</span></span>  
  
 [!code-vb[VbXMLSamples#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_1.vb)]  
  
 <span data-ttu-id="db8f0-190">Örneğin, aşağıdaki metni görüntüler.</span><span class="sxs-lookup"><span data-stu-id="db8f0-190">The example displays the following text.</span></span> <span data-ttu-id="db8f0-191">Değişmez değeri boş öğeleri yapısını korur dikkat edin.</span><span class="sxs-lookup"><span data-stu-id="db8f0-191">Notice that the literal preserves the structure of the empty elements.</span></span>  
  
```xml  
<outer>  
  <inner1></inner1>  
  <inner2 />  
</outer>  
```  
  
## <a name="example"></a><span data-ttu-id="db8f0-192">Örnek</span><span class="sxs-lookup"><span data-stu-id="db8f0-192">Example</span></span>  
 <span data-ttu-id="db8f0-193">Aşağıdaki örnek katıştırılmış ifadeler bir öğe adı ve öznitelikler oluşturmak için nasıl kullanılacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="db8f0-193">The following example shows how to use embedded expressions to name an element and create attributes.</span></span>  
  
 [!code-vb[VbXMLSamples#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_2.vb)]  
  
 <span data-ttu-id="db8f0-194">Bu kod, aşağıdaki metni görüntüler:</span><span class="sxs-lookup"><span data-stu-id="db8f0-194">This code displays the following text:</span></span>  
  
```xml  
<book isbn="1234" author="My Author" year="1999" title="My Book" />  
```  
  
## <a name="example"></a><span data-ttu-id="db8f0-195">Örnek</span><span class="sxs-lookup"><span data-stu-id="db8f0-195">Example</span></span>  
 <span data-ttu-id="db8f0-196">Aşağıdaki örnek bildirir `ns` bir XML ad alanı öneki olarak.</span><span class="sxs-lookup"><span data-stu-id="db8f0-196">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="db8f0-197">XML değişmez değer oluşturmak için ad alanı öneki kullanıyor ve öğenin son form görüntüler.</span><span class="sxs-lookup"><span data-stu-id="db8f0-197">It then uses the prefix of the namespace to create an XML literal and displays the element's final form.</span></span>  
  
 [!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_3.vb)]  
  
 <span data-ttu-id="db8f0-198">Bu kod, aşağıdaki metni görüntüler:</span><span class="sxs-lookup"><span data-stu-id="db8f0-198">This code displays the following text:</span></span>  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 <span data-ttu-id="db8f0-199">Derleyici XML ad alanı için bir önek tanım genel XML ad alanı öneki dönüştürülen dikkat edin.</span><span class="sxs-lookup"><span data-stu-id="db8f0-199">Notice that the compiler converted the prefix of the global XML namespace into a prefix definition for the XML namespace.</span></span> <span data-ttu-id="db8f0-200">\<Ns:middle > öğesi için XML ad alanı önekini yeniden tanımlamaktadır \<ns:inner1 > öğesi.</span><span class="sxs-lookup"><span data-stu-id="db8f0-200">The \<ns:middle> element redefines the XML namespace prefix for the \<ns:inner1> element.</span></span> <span data-ttu-id="db8f0-201">Ancak, \<ns:inner2 > öğesi tarafından tanımlanan ad alanı kullanır `Imports` deyimi.</span><span class="sxs-lookup"><span data-stu-id="db8f0-201">However, the \<ns:inner2> element uses the namespace defined by the `Imports` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db8f0-202">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="db8f0-202">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 [<span data-ttu-id="db8f0-203">Bildirilmiş XML öğeleri ve özniteliklerinin adları</span><span class="sxs-lookup"><span data-stu-id="db8f0-203">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)  
 [<span data-ttu-id="db8f0-204">XML açıklama değişmez değeri</span><span class="sxs-lookup"><span data-stu-id="db8f0-204">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)  
 [<span data-ttu-id="db8f0-205">XML CDATA değişmez değeri</span><span class="sxs-lookup"><span data-stu-id="db8f0-205">XML CDATA Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)  
 [<span data-ttu-id="db8f0-206">XML değişmez değerleri</span><span class="sxs-lookup"><span data-stu-id="db8f0-206">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="db8f0-207">Visual Basic'de XML oluşturma</span><span class="sxs-lookup"><span data-stu-id="db8f0-207">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="db8f0-208">XML'de katıştırılmış ifadeler</span><span class="sxs-lookup"><span data-stu-id="db8f0-208">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [<span data-ttu-id="db8f0-209">Imports deyimi (XML Namespace)</span><span class="sxs-lookup"><span data-stu-id="db8f0-209">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)