# intellij-live-code-template
IntellijIdea live code templates using **Velocity**

To use these code templates.You must create live templates foreach code snippet in your IDE.(https://www.jetbrains.com/help/idea/creating-and-editing-live-templates.html)

1. Domain Creation


    The following template will create domain entity.
    
                  #if (${PACKAGE_NAME} && ${PACKAGE_NAME} != "")package ${PACKAGE_NAME};#end
                  #parse("File Header.java")
                  #if(${ID_TYPE}=="string")
                  import org.hibernate.annotations.GenericGenerator;
                  #end
                  import javax.persistence.*;

                  @Entity
                  public class ${Entity_name}{
                      #if(${ID_TYPE} =="string")
                      @Id
                      @GeneratedValue(generator = "uuid2")
                      @GenericGenerator(name = "uuid2" , strategy = "uuid2")
                      private String id;
                      #elseif(${ID_TYPE} == "Long"||${ID_TYPE}=="Integer")
                      @Id
                      private ${ID_TYPE} id;
                      #else
                      @Id
                      private Long id;
                      #end
                  }

