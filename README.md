# XML_Beans
 









Use Apache XMLBeans tool and JAXB to manipulate XML and Java Objects.


Purpose:
1.	We want to infer a XML schema from an existing XML document.
2.	We want to programmatically manipulate the “DOM” objects in the XML so that we can programmatically modify, add, and delete information in the XML.

Possible solution:
1.	We can use a utility to infer a XML schema from a XML file.
2.	Then we use another utility to generate programmable classes/objects from the inferred XML schema.
3.	We can then manipulate those classes/objects in computer memory.
4.	Finally, we use a utility to convert the manipulated objects back into a XML file.

Consider a very simple XML example, cd_catalog.xml.  The root element is <GATALOG>:
 
<?xml version="1.0" encoding="UTF-8"?>
<CATALOG>
  <CD>
    <TITLE>Empire Burlesque</TITLE>
    <ARTIST>Bob Dylan</ARTIST>
    <COUNTRY>USA</COUNTRY>
    <COMPANY>Columbia</COMPANY>
    <PRICE>10.90</PRICE>
    <YEAR>1985</YEAR>
  </CD>
  <CD>
    <TITLE>Hide your heart</TITLE>
    <ARTIST>Bonnie Tyler</ARTIST>
    <COUNTRY>UK</COUNTRY>
    <COMPANY>CBS Records</COMPANY>
    <PRICE>9.90</PRICE>
    <YEAR>1988</YEAR>
  </CD>
  <CD>
    <TITLE>Greatest Hits</TITLE>
    <ARTIST>Dolly Parton</ARTIST>
    <COUNTRY>USA</COUNTRY>
    <COMPANY>RCA</COMPANY>
    <PRICE>9.90</PRICE>
    <YEAR>1982</YEAR>
  </CD>
  <CD>
    <TITLE>Still got the blues</TITLE>
    <ARTIST>Gary Moore</ARTIST>
    <COUNTRY>UK</COUNTRY>
    <COMPANY>Virgin records</COMPANY>
    <PRICE>10.20</PRICE>
    <YEAR>1990</YEAR>
  </CD>
  <CD>
    <TITLE>Eros</TITLE>
    <ARTIST>Eros Ramazzotti</ARTIST>
    <COUNTRY>EU</COUNTRY>
    <COMPANY>BMG</COMPANY>
    <PRICE>9.90</PRICE>
    <YEAR>1997</YEAR>
  </CD>
  <CD>
    <TITLE>One night only</TITLE>
    <ARTIST>Bee Gees</ARTIST>
    <COUNTRY>UK</COUNTRY>
    <COMPANY>Polydor</COMPANY>
    <PRICE>10.90</PRICE>
    <YEAR>1998</YEAR>
  </CD>
  <CD>
    <TITLE>Sylvias Mother</TITLE>
    <ARTIST>Dr.Hook</ARTIST>
    <COUNTRY>UK</COUNTRY>
    <COMPANY>CBS</COMPANY>
    <PRICE>8.10</PRICE>
    <YEAR>1973</YEAR>
  </CD>
  <CD>
    <TITLE>Maggie May</TITLE>
    <ARTIST>Rod Stewart</ARTIST>
    <COUNTRY>UK</COUNTRY>
    <COMPANY>Pickwick</COMPANY>
    <PRICE>8.50</PRICE>
    <YEAR>1990</YEAR>
  </CD>
  <CD>
    <TITLE>Romanza</TITLE>
    <ARTIST>Andrea Bocelli</ARTIST>
    <COUNTRY>EU</COUNTRY>
    <COMPANY>Polydor</COMPANY>
    <PRICE>10.80</PRICE>
    <YEAR>1996</YEAR>
  </CD>
  <CD>
    <TITLE>When a man loves a woman</TITLE>
    <ARTIST>Percy Sledge</ARTIST>
    <COUNTRY>USA</COUNTRY>
    <COMPANY>Atlantic</COMPANY>
    <PRICE>8.70</PRICE>
    <YEAR>1987</YEAR>
  </CD>
  <CD>
    <TITLE>Black angel</TITLE>
    <ARTIST>Savage Rose</ARTIST>
    <COUNTRY>EU</COUNTRY>
    <COMPANY>Mega</COMPANY>
    <PRICE>10.90</PRICE>
    <YEAR>1995</YEAR>
  </CD>
  <CD>
    <TITLE>1999 Grammy Nominees</TITLE>
    <ARTIST>Many</ARTIST>
    <COUNTRY>USA</COUNTRY>
    <COMPANY>Grammy</COMPANY>
    <PRICE>10.20</PRICE>
    <YEAR>1999</YEAR>
  </CD>
  <CD>
    <TITLE>For the good times</TITLE>
    <ARTIST>Kenny Rogers</ARTIST>
    <COUNTRY>UK</COUNTRY>
    <COMPANY>Mucik Master</COMPANY>
    <PRICE>8.70</PRICE>
    <YEAR>1995</YEAR>
  </CD>
  <CD>
    <TITLE>Big Willie style</TITLE>
    <ARTIST>Will Smith</ARTIST>
    <COUNTRY>USA</COUNTRY>
    <COMPANY>Columbia</COMPANY>
    <PRICE>9.90</PRICE>
    <YEAR>1997</YEAR>
  </CD>
  <CD>
    <TITLE>Tupelo Honey</TITLE>
    <ARTIST>Van Morrison</ARTIST>
    <COUNTRY>UK</COUNTRY>
    <COMPANY>Polydor</COMPANY>
    <PRICE>8.20</PRICE>
    <YEAR>1971</YEAR>
  </CD>
  <CD>
    <TITLE>Soulsville</TITLE>
    <ARTIST>Jorn Hoel</ARTIST>
    <COUNTRY>Norway</COUNTRY>
    <COMPANY>WEA</COMPANY>
    <PRICE>7.90</PRICE>
    <YEAR>1996</YEAR>
  </CD>
  <CD>
    <TITLE>The very best of</TITLE>
    <ARTIST>Cat Stevens</ARTIST>
    <COUNTRY>UK</COUNTRY>
    <COMPANY>Island</COMPANY>
    <PRICE>8.90</PRICE>
    <YEAR>1990</YEAR>
  </CD>
  <CD>
    <TITLE>Stop</TITLE>
    <ARTIST>Sam Brown</ARTIST>
    <COUNTRY>UK</COUNTRY>
    <COMPANY>A and M</COMPANY>
    <PRICE>8.90</PRICE>
    <YEAR>1988</YEAR>
  </CD>
  <CD>
    <TITLE>Bridge of Spies</TITLE>
    <ARTIST>T'Pau</ARTIST>
    <COUNTRY>UK</COUNTRY>
    <COMPANY>Siren</COMPANY>
    <PRICE>7.90</PRICE>
    <YEAR>1987</YEAR>
  </CD>
  <CD>
    <TITLE>Private Dancer</TITLE>
    <ARTIST>Tina Turner</ARTIST>
    <COUNTRY>UK</COUNTRY>
    <COMPANY>Capitol</COMPANY>
    <PRICE>8.90</PRICE>
    <YEAR>1983</YEAR>
  </CD>
  <CD>
    <TITLE>Midt om natten</TITLE>
    <ARTIST>Kim Larsen</ARTIST>
    <COUNTRY>EU</COUNTRY>
    <COMPANY>Medley</COMPANY>
    <PRICE>7.80</PRICE>
    <YEAR>1983</YEAR>
  </CD>
  <CD>
    <TITLE>Pavarotti Gala Concert</TITLE>
    <ARTIST>Luciano Pavarotti</ARTIST>
    <COUNTRY>UK</COUNTRY>
    <COMPANY>DECCA</COMPANY>
    <PRICE>9.90</PRICE>
    <YEAR>1991</YEAR>
  </CD>
  <CD>
    <TITLE>The dock of the bay</TITLE>
    <ARTIST>Otis Redding</ARTIST>
    <COUNTRY>USA</COUNTRY>
    <COMPANY>Stax Records</COMPANY>
    <PRICE>7.90</PRICE>
    <YEAR>1968</YEAR>
  </CD>
  <CD>
    <TITLE>Picture book</TITLE>
    <ARTIST>Simply Red</ARTIST>
    <COUNTRY>EU</COUNTRY>
    <COMPANY>Elektra</COMPANY>
    <PRICE>7.20</PRICE>
    <YEAR>1985</YEAR>
  </CD>
  <CD>
    <TITLE>Red</TITLE>
    <ARTIST>The Communards</ARTIST>
    <COUNTRY>UK</COUNTRY>
    <COMPANY>London</COMPANY>
    <PRICE>7.80</PRICE>
    <YEAR>1987</YEAR>
  </CD>
  <CD>
    <TITLE>Unchain my heart</TITLE>
    <ARTIST>Joe Cocker</ARTIST>
    <COUNTRY>USA</COUNTRY>
    <COMPANY>EMI</COMPANY>
    <PRICE>8.20</PRICE>
    <YEAR>1987</YEAR>
  </CD>
</CATALOG>
 
Implementation Steps

Go to your project root directory:
cd C:\Projects\XML_Project
The directory contains a Tool directory where XMLBeans utility resides and a Code directory where all coding related files reside.  

Generate XML schema from XML file by inst2xsd (instance to xsd) of XMLbeans package:
.\Tool\xmlbeans-5.0.0\bin\inst2xsd .\Code\cd_catalog.xml -outDir .\Code -outPrefix cd_catalog
The above command generates cd_catalog0.xsd file from cd_catalog.xml

Use Java JAXB library tool xjc to generate Java source code from XML schema (XSD):
xjc -d .\Code\src -p example.xjc -b .\Code\bindings.xml .\Code\cd_catalog0.xsd
Note: Java needs to be installed first.  JAXB should come with Java.
-d: destination directory where generated source code will be in
-p: application package, can name anything as your java application package
-b: binding XML file where generated class names can be specified.
The above command generates 3 files from cd_catalog0.xsd:
1.	Catalog.java
2.	CD.java
3.	ObjectFactory.java

Use Eclipse IDE to do Java coding

Create a Java Project in Eclipse:

 

Choose Code\src as the source folder and remove other folders:
 

Modify Category.java:
In Category.java, locate @XmlType(name = "CATALOGType"...), change "CATALOGType" to "CATALOG".  
Add root annotation @XmlRootElement(name = "CATALOG") to Catalog.java.
Add constructor, toString(), and addACD() methonds:
public Catalog() {
		this.cd = new ArrayList<CD>();
	}

	@Override
	public String toString() {

		StringBuilder str = new StringBuilder("[");
		for (CD aCD : cd) {
			str.append(aCD);
			str.append(" | ");
		}

		str.append("]");

		return str.toString();
	}

	public void addACD(CD aCD) {
		this.cd.add(aCD);
	}

Modify CD.java:
In CD.java, locate @XmlType(name = "CDType"...), change "CDType" to "CD".
Add toString() method for debug printing:
@Override
public String toString() {
return "title: " + this.title + ", artist: " + this.artist + ", company: " + this.company + ", country: "
	+ this.country + ", price: " + this.price + ", year: " + this.year;

}


Create a main java class (See MainApplication.java): 
Implement methods that use JAXB unmarshal (XML to Java objects) and marshal (Java objects to XML).

public static void unmarshallTest() {
try {
		JAXBContext jaxbContext = JAXBContext.newInstance(Catalog.class);

		
		Unmarshaller jaxbUnmarshaller = jaxbContext.createUnmarshaller();

		// Unmarshalling (Convert XML instance into Java objects)
Catalog catalog = (Catalog) jaxbUnmarshaller.unmarshal(new   File("C:\\Projects\\XML_Project\\Code\\cd_catalog.xml"));

		System.out.println(catalog);

	} catch (JAXBException e) {

		e.printStackTrace();
	}
}

public static void marshallTest() {
		
	//Create a Catalog object
	Catalog catalog = new Catalog();

	//Create a CD object
	CD cd = new CD();
	cd.setARTIST("Yunpeng Li");
	cd.setCOMPANY("BAE");
	cd.setCOUNTRY("USA");
	cd.setPRICE(15);
	cd.setTITLE("Enigma");
	cd.setYEAR(Short.valueOf("2021"));

	//Add the new CD object into the Catalog object
	catalog.addACD(cd);

	JAXBContext jaxbContext;
	try {

		jaxbContext = JAXBContext.newInstance(Catalog.class);

		Marshaller jaxbMarshaller = jaxbContext.createMarshaller();

File file = new File("C:\\Projects\\XML_Project\\Code\\cd_catalog_new.xml");
		
// output pretty printed
		jaxbMarshaller.setProperty(Marshaller.JAXB_FORMATTED_OUTPUT, true);

		// Marshalling (Convert Java objects into XML)
		jaxbMarshaller.marshal(catalog, file);
		jaxbMarshaller.marshal(catalog, System.out);
	} catch (JAXBException e) {
		e.printStackTrace();
	}

}

Now we can programmatically load existing XML file and create Java object representation from it, then we can add or modify the values in Java objects and marshal back to XML format.

To run MainApplication.java in Eclipse:
 

TODO: Use Java GUI to manipulate CD objects in Catalog.


Useful Links:

Apache XMLBeans:
https://xmlbeans.apache.org/

JAXB: Generate Classes from XSD:
https://examples.javacodegeeks.com/core-java/xml/bind/jaxb-generate-classes-xsd/

Marshalling and Unmarshalling in JAXB:
https://dzone.com/articles/introduction-to-jaxb-20

Eclipse Download:
https://www.eclipse.org/

