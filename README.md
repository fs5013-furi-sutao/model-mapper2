# model-mapper2

``` java
ModelMapper mapper = new ModelMapper();

TypeMap<DeviceConnectorDto, DeviceDto> propertyMapper = 
        mapper.createTypeMap(DeviceConnectorDto.class,DeviceDto.class);

propertyMapper.addMappings(map -> map.skip(DeviceDto::setAge));

propertyMapper.addMappings(
    map -> map.map(DeviceConnectorDto::getPrice, DeviceDto::setDeviceId)
);

DeviceDto deviceDto = mapper.map(deviceConnectorDto, DeviceDto.class);
```
