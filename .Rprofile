if (interactive()) {
  message("Checking GitHub for updates...")
  
  tryCatch({
    result <- suppressWarnings(
      system2(
        "git",
        c("pull", "--ff-only"),
        stdout = TRUE,
        stderr = TRUE
      )
    )
    
    status <- attr(result, "status")
    
    if (is.null(status) || status == 0) {
      message("GitHub sync successful!")
    } else {
      message("GitHub sync failed. Check Git configuration or local changes.")
    }
  }, error = function(e) {
    message("GitHub sync error: ", conditionMessage(e))
  })
}
