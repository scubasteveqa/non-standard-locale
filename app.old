library(shiny)
library(bslib)

ui <- page_fluid(
  theme = bs_theme(bootswatch = "cerulean"),
  
  h1("Locale and Encoding Test App"),
  
  card(
    card_header("Current System Locale"),
    card_body(
      verbatimTextOutput("locale_info")
    )
  ),
  
  card(
    card_header("Japanese Text Display Test"),
    card_body(
      p("The following text should display properly if encoding is set correctly:"),
      h3("日本語のテキスト (Japanese Text)"),
      p("こんにちは、世界! (Hello, World!)"),
      p("これは文字エンコーディングのテストです。 (This is a text encoding test.)")
    )
  ),
  
  card(
    card_header("Character Encoding Test"),
    card_body(
      p("Special characters from various languages:"),
      p("German: äöüß"),
      p("French: éèêëçàâ"),
      p("Russian: Привет мир"),
      p("Greek: Γειά σου Κόσμε"),
      p("Arabic: مرحبا بالعالم"),
      p("Thai: สวัสดีชาวโลก"),
      p("Chinese: 你好，世界")
    )
  )
)

server <- function(input, output, session) {
  output$locale_info <- renderPrint({
    cat("Locale settings:\n")
    cat("----------------\n")
    print(Sys.getlocale())
    
    cat("\n\nEncoding information:\n")
    cat("--------------------\n")
    cat("Default encoding: ", getOption("encoding"), "\n")
    cat("Native encoding: ", localeToCharset(), "\n")
  })
}

shinyApp(ui = ui, server = server)

