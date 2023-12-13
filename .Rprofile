new_post <- function(slug) {
  if (grepl("[^[:alnum:]-]", slug)) {
    stop("Slug can't contain special characters")
  }
  
  date <- Sys.Date() |> as.character()
  final_slug <- paste0(date, "-", slug)
  name_dir <- file.path("posts", final_slug)
  name_file <- file.path(name_dir, "index.qmd")
    
  dir.create(name_dir)
  file.create(name_file)
  
  lines <- c(
    '---',
    'title: "Title"',
    'author: Samuel Calderon',
    paste0('date: "', date, '"'),
    'knitr:',
    '  opts_chunk:',
    '    comment: "#>"',
    '    class-output: "text-muted"',
    '    class-error: "text-danger"',
    '---',
    '',
    ''
  )
  
  file_con <- file(name_file)
  writeLines(lines, file_con)
  close(file_con)
  
  message("New post created!")
}
