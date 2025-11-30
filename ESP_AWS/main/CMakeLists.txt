idf_component_register(SRCS "main.c"
                       PRIV_REQUIRES spi_flash
                       INCLUDE_DIRS ""
                       REQUIRES esp_wifi nvs_flash esp_event esp_netif mqtt json)

# Embed the certificates into the binary
target_add_binary_data(${COMPONENT_TARGET} "certs/root_ca.pem" TEXT)
target_add_binary_data(${COMPONENT_TARGET} "certs/device.crt" TEXT)
target_add_binary_data(${COMPONENT_TARGET} "certs/private.key" TEXT)

target_add_binary_data(${COMPONENT_TARGET} "certs/config.json" TEXT)