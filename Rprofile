# .Rprofile
# Set proxy environment variables
Sys.setenv(http_proxy = "http://proxy.fsh.hdwa.health.wa.gov.au:8080")
Sys.setenv(https_proxy = "http://proxy.fsh.hdwa.health.wa.gov.au:8080")

# Set additional options
options(warn = -1)
options(internet.info = 0)
options(download.file.method = "libcurl")
options(internet2 = FALSE)
options(httr_oauth_cache = FALSE) # For httr package
Sys.setenv(RCURL_VERBOSE = 0) # For curl package

# Set R library paths
Sys.setenv(R_LIBS_USER = "W:/Pathology/FSH/Immunology/Validation Data and Research Projects (AD13)/Bioinformatics Projects/2022-000 Bioinformatics resources/R/library")
Sys.setenv(R_LIBS_SITE = "W:/Pathology/FSH/Immunology/Validation Data and Research Projects (AD13)/Bioinformatics Projects/2022-000 Bioinformatics resources/R/library")

# Update .libPaths() to include the new library paths
.libPaths("W:/Pathology/FSH/Immunology/Validation Data and Research Projects (AD13)/Bioinformatics Projects/2022-000 Bioinformatics resources/R/library")
