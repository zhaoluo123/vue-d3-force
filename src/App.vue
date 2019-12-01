<template>
  <div id="app">
    <div id="graph"></div>
  </div>
</template>

<script>
    import * as d3 from "d3";
    import {
        getNodeSelfPath,
        setLinkGroup,
        getNodesLine,} from './utils/deviceRelation'

export default {
    mounted() {
        let data = {
            "links": [{
                "source": 0,
                "target": 1,
                "relation": {
                    "relationshipId": 200,
                    "relationship": "BELONG_APPLICATION",
                    "created": 1574822650825,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 2,
                "target": 3,
                "relation": {
                    "relationshipId": 135,
                    "relationship": "EFFECT_LOCATION",
                    "created": 1574821264333,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 6,
                "target": 7,
                "relation": {
                    "relationshipId": 123,
                    "relationship": "BELONG_MANUFACTURER",
                    "created": 1574143813834,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 8,
                "target": 9,
                "relation": {
                    "relationshipId": 132,
                    "relationship": "PARENT",
                    "created": 1571109959476,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 10,
                "target": 11,
                "relation": {
                    "relationshipId": 145,
                    "relationship": "AUTHORIZE_APPLICATION",
                    "created": 1574409066966,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 12,
                "target": 13,
                "relation": {
                    "relationshipId": 103,
                    "relationship": "BELONG_APPLICATION",
                    "created": 1574229503622,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 14,
                "target": 15,
                "relation": {
                    "relationshipId": 95,
                    "relationship": "AUTHORIZE_APPLICATION",
                    "created": 1574218526058,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 0,
                "target": 16,
                "relation": {
                    "relationshipId": 202,
                    "relationship": "EFFECT_LOCATION",
                    "created": 1574825180239,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 19,
                "target": 20,
                "relation": {
                    "relationshipId": 180,
                    "relationship": "CONTROL",
                    "created": 1574652545781,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 2,
                "target": 2,
                "relation": {
                    "relationshipId": 198,
                    "relationship": "PARENT",
                    "created": 1574821366951,
                    "lineNumber": 1,
                    "isSelf": true
                }
            }, {
                "source": 8,
                "target": 22,
                "relation": {
                    "relationshipId": 141,
                    "relationship": "PARENT",
                    "created": 1571189421890,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 10,
                "target": 10,
                "relation": {
                    "relationshipId": 163,
                    "relationship": "PARENT",
                    "created": 1574409116976,
                    "lineNumber": 1,
                    "isSelf": true
                }
            }, {
                "source": 9,
                "target": 8,
                "relation": {
                    "relationshipId": 131,
                    "relationship": "CONTROL",
                    "created": 1571109777550,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 25,
                "target": 26,
                "relation": {
                    "relationshipId": 182,
                    "relationship": "EFFECT_LOCATION",
                    "created": 1574734111195,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 6,
                "target": 6,
                "relation": {
                    "relationshipId": 12,
                    "relationship": "PARENT",
                    "created": 1574142984212,
                    "lineNumber": 1,
                    "isSelf": true
                }
            }, {
                "source": 8,
                "target": 28,
                "relation": {
                    "relationshipId": 60,
                    "relationship": "PARENT",
                    "created": 1571189421890,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 29,
                "target": 22,
                "relation": {
                    "relationshipId": 118,
                    "relationship": "PARENT",
                    "created": 1571281100918,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 30,
                "target": 31,
                "relation": {
                    "relationshipId": 82,
                    "relationship": "BELONG_MANUFACTURER",
                    "created": 1574842004656,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 0,
                "target": 32,
                "relation": {
                    "relationshipId": 199,
                    "relationship": "CONNECT_PLATFORM",
                    "created": 1574822498689,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 33,
                "target": 34,
                "relation": {
                    "relationshipId": 68,
                    "relationship": "CONTROL",
                    "created": 1570777779101,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 29,
                "target": 35,
                "relation": {
                    "relationshipId": 3,
                    "relationship": "PARENT",
                    "created": 1571281100918,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 2,
                "target": 36,
                "relation": {
                    "relationshipId": 194,
                    "relationship": "CONNECT_PLATFORM",
                    "created": 1574821180519,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 37,
                "target": 38,
                "relation": {
                    "relationshipId": 190,
                    "relationship": "BELONG_ADMIN",
                    "created": 1574745879106,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 40,
                "target": 41,
                "relation": {
                    "relationshipId": 1,
                    "relationship": "BELONG_MANUFACTURER",
                    "created": 1574130631578,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 8,
                "target": 35,
                "relation": {
                    "relationshipId": 98,
                    "relationship": "PARENT",
                    "created": 1571189421890,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 10,
                "target": 42,
                "relation": {
                    "relationshipId": 138,
                    "relationship": "BELONG_APPLICATION",
                    "created": 1574408689645,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 33,
                "target": 34,
                "relation": {
                    "relationshipId": 66,
                    "relationship": "PARENT",
                    "created": 1570777635645,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 2,
                "target": 2,
                "relation": {
                    "relationshipId": 192,
                    "relationship": "CONTROL",
                    "created": 1574821284400,
                    "lineNumber": 2,
                    "isSelf": true
                }
            }, {
                "source": 14,
                "target": 15,
                "relation": {
                    "relationshipId": 94,
                    "relationship": "BELONG_APPLICATION",
                    "created": 1574218478704,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 44,
                "target": 9,
                "relation": {
                    "relationshipId": 11,
                    "relationship": "PARENT",
                    "created": 1571189497514,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 10,
                "target": 45,
                "relation": {
                    "relationshipId": 183,
                    "relationship": "PARENT",
                    "created": 1574734473815,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 46,
                "target": 47,
                "relation": {
                    "relationshipId": 108,
                    "relationship": "BELONG_MANUFACTURER",
                    "created": 1574401675435,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 10,
                "target": 48,
                "relation": {
                    "relationshipId": 185,
                    "relationship": "EFFECT_LOCATION",
                    "created": 1574735098436,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 30,
                "target": 49,
                "relation": {
                    "relationshipId": 92,
                    "relationship": "BELONG_ADMIN",
                    "created": 1574842038292,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 30,
                "target": 50,
                "relation": {
                    "relationshipId": 102,
                    "relationship": "BELONG_ADMIN",
                    "created": 1574842038292,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 2,
                "target": 1,
                "relation": {
                    "relationshipId": 196,
                    "relationship": "BELONG_APPLICATION",
                    "created": 1574821237662,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 51,
                "target": 52,
                "relation": {
                    "relationshipId": 39,
                    "relationship": "PARENT",
                    "created": 1571040502085,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 37,
                "target": 53,
                "relation": {
                    "relationshipId": 191,
                    "relationship": "BELONG_ADMIN",
                    "created": 1574745879106,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 8,
                "target": 54,
                "relation": {
                    "relationshipId": 77,
                    "relationship": "PARENT",
                    "created": 1571189421890,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 55,
                "target": 56,
                "relation": {
                    "relationshipId": 130,
                    "relationship": "EFFECT_LOCATION",
                    "created": 1574322233908,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 30,
                "target": 13,
                "relation": {
                    "relationshipId": 133,
                    "relationship": "AUTHORIZE_APPLICATION",
                    "created": 1574842153352,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 0,
                "target": 58,
                "relation": {
                    "relationshipId": 201,
                    "relationship": "BELONG_MANUFACTURER",
                    "created": 1574825160187,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 34,
                "target": 33,
                "relation": {
                    "relationshipId": 100,
                    "relationship": "CONTROL",
                    "created": 1570779022030,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 19,
                "target": 59,
                "relation": {
                    "relationshipId": 99,
                    "relationship": "BELONG_APPLICATION",
                    "created": 1574652203566,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 8,
                "target": 44,
                "relation": {
                    "relationshipId": 143,
                    "relationship": "PARENT",
                    "created": 1571189421890,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 44,
                "target": 8,
                "relation": {
                    "relationshipId": 139,
                    "relationship": "PARENT",
                    "created": 1571122040940,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 44,
                "target": 22,
                "relation": {
                    "relationshipId": 124,
                    "relationship": "PARENT",
                    "created": 1571189497514,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 45,
                "target": 61,
                "relation": {
                    "relationshipId": 187,
                    "relationship": "BELONG_MANUFACTURER",
                    "created": 1574736042772,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 30,
                "target": 62,
                "relation": {
                    "relationshipId": 181,
                    "relationship": "AUTHORIZE_APPLICATION",
                    "created": 1574842153352,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 44,
                "target": 28,
                "relation": {
                    "relationshipId": 10,
                    "relationship": "PARENT",
                    "created": 1571189497514,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 44,
                "target": 54,
                "relation": {
                    "relationshipId": 128,
                    "relationship": "PARENT",
                    "created": 1571189497514,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 10,
                "target": 63,
                "relation": {
                    "relationshipId": 184,
                    "relationship": "EFFECT_LOCATION",
                    "created": 1574735076416,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 14,
                "target": 14,
                "relation": {
                    "relationshipId": 93,
                    "relationship": "PARENT",
                    "created": 1574217786986,
                    "lineNumber": 1,
                    "isSelf": true
                }
            }, {
                "source": 64,
                "target": 65,
                "relation": {
                    "relationshipId": 44,
                    "relationship": "CONNECT_PLATFORM",
                    "created": 1574758583985,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 29,
                "target": 8,
                "relation": {
                    "relationshipId": 43,
                    "relationship": "PARENT",
                    "created": 1571281100918,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 10,
                "target": 67,
                "relation": {
                    "relationshipId": 23,
                    "relationship": "BELONG_MANUFACTURER",
                    "created": 1574408725149,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 2,
                "target": 68,
                "relation": {
                    "relationshipId": 195,
                    "relationship": "BELONG_ADMIN",
                    "created": 1574821199052,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 10,
                "target": 10,
                "relation": {
                    "relationshipId": 9,
                    "relationship": "CONTROL",
                    "created": 1574408971838,
                    "lineNumber": 2,
                    "isSelf": true
                }
            }, {
                "source": 71,
                "target": 71,
                "relation": {
                    "relationshipId": 46,
                    "relationship": "CONTROL",
                    "created": 1571721495529,
                    "lineNumber": 1,
                    "isSelf": true
                }
            }, {
                "source": 2,
                "target": 73,
                "relation": {
                    "relationshipId": 197,
                    "relationship": "BELONG_MANUFACTURER",
                    "created": 1574821249233,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 74,
                "target": 10,
                "relation": {
                    "relationshipId": 45,
                    "relationship": "CONTROL",
                    "created": 1574401909220,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 19,
                "target": 75,
                "relation": {
                    "relationshipId": 117,
                    "relationship": "CONTROL",
                    "created": 1574652545781,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 6,
                "target": 76,
                "relation": {
                    "relationshipId": 144,
                    "relationship": "CONTROL",
                    "created": 1574142879454,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 8,
                "target": 8,
                "relation": {
                    "relationshipId": 142,
                    "relationship": "PARENT",
                    "created": 1571189421890,
                    "lineNumber": 1,
                    "isSelf": true
                }
            }, {
                "source": 10,
                "target": 63,
                "relation": {
                    "relationshipId": 186,
                    "relationship": "INSTALL_LOCATION",
                    "created": 1574735183907,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 52,
                "target": 51,
                "relation": {
                    "relationshipId": 122,
                    "relationship": "CONTROL",
                    "created": 1571040489911,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 2,
                "target": 77,
                "relation": {
                    "relationshipId": 193,
                    "relationship": "INSTALL_LOCATION",
                    "created": 1574821301840,
                    "lineNumber": null,
                    "isSelf": false
                }
            }, {
                "source": 44,
                "target": 35,
                "relation": {
                    "relationshipId": 79,
                    "relationship": "PARENT",
                    "created": 1571189497514,
                    "lineNumber": null,
                    "isSelf": false
                }
            }],
            "nodes": [{
                "id": 1,
                "deviceId": "002101025d09c809e4b0ca3a6a0966d2",
                "factoryCode": "061901",
                "modelCode": "00210102",
                "label": "Device",
                "linkId": 0
            }, {
                "id": 43,
                "applicationName": "测试盘古",
                "appId": "com.huawei.pangu",
                "label": "Application",
                "linkId": 1
            }, {
                "id": 18,
                "deviceId": "004801055dd4f157e4b04845806d6671",
                "factoryCode": "1120device002",
                "modelCode": "00480105",
                "label": "Device",
                "linkId": 2
            }, {
                "id": 140,
                "positionNumber": "887",
                "positionCode": "098",
                "label": "Position",
                "linkId": 3
            }, {
                "id": 86,
                "deviceId": "huo1a1005d5647ed270e07fad941eb33",
                "factoryCode": "huo11111111ww",
                "modelCode": "huoaa01a100",
                "label": "Device",
                "linkId": 4
            }, {
                "id": 125,
                "deviceId": "hye029015dc3b5df270e2cc0b2a2641c",
                "factoryCode": "dsafafaf666",
                "modelCode": "hye02901",
                "label": "Device",
                "linkId": 5
            }, {
                "id": 24,
                "deviceId": "000801025d0c7e438466e74289f900ef",
                "factoryCode": "buchongceshi2",
                "modelCode": "00080102",
                "label": "Device",
                "linkId": 6
            }, {
                "id": 163,
                "manufacturerCode": "HJJc",
                "manufacturerName": "测试厂商",
                "label": "Manufacturer",
                "linkId": 7
            }, {
                "id": 118,
                "deviceId": "004901015da53819e4b0bf772bd36775",
                "factoryCode": "13241341324143",
                "modelCode": null,
                "label": "Device",
                "linkId": 8
            }, {
                "id": 121,
                "deviceId": "004901015da53785e4b0bf772bd36774",
                "factoryCode": "58656745",
                "modelCode": "00490101",
                "label": "Device",
                "linkId": 9
            }, {
                "id": 2,
                "deviceId": "004101015dd7502ae4b0c5015d3aebe8",
                "factoryCode": "test1234",
                "modelCode": "00410101",
                "label": "Device",
                "linkId": 10
            }, {
                "id": 122,
                "applicationName": "测试2",
                "appId": "ceshi2",
                "label": "Application",
                "linkId": 11
            }, {
                "id": 105,
                "deviceId": "aa01a1005dce4dde0bfb1be4b75abe40",
                "factoryCode": "632598",
                "modelCode": "00080101",
                "label": "Device",
                "linkId": 12
            }, {
                "id": 131,
                "applicationName": "云企划2",
                "appId": "experienceUser",
                "label": "Application",
                "linkId": 13
            }, {
                "id": 111,
                "deviceId": "000901015d269b8bf140f7aa0df8b95a",
                "factoryCode": "0711002",
                "modelCode": "00090101",
                "label": "Device",
                "linkId": 14
            }, {
                "id": 113,
                "applicationName": "天行健111",
                "appId": "123344121",
                "label": "Application",
                "linkId": 15
            }, {
                "id": 165,
                "positionNumber": "009",
                "positionCode": "980",
                "label": "Position",
                "linkId": 16
            }, {
                "id": 137,
                "deviceId": "004101015dd64d90e4b0c5015d3aebe1",
                "factoryCode": "191018002",
                "modelCode": "00410101",
                "label": "Device",
                "linkId": 17
            }, {
                "id": 19,
                "deviceId": "pin1a1005d5647ed270e07fad941eb33",
                "factoryCode": "pin11111ww",
                "modelCode": "pin1a100",
                "label": "Device",
                "linkId": 18
            }, {
                "id": 20,
                "deviceId": "005601015dc50794e4b080f28a960a2c",
                "factoryCode": "0513",
                "modelCode": "00560101",
                "label": "Device",
                "linkId": 19
            }, {
                "id": 112,
                "deviceId": "000101035dc5310ce4b041b08987f1f8",
                "factoryCode": "05131",
                "modelCode": "00010103",
                "label": "Device",
                "linkId": 20
            }, {
                "id": 147,
                "deviceId": "sha1a1005d5647ed270e07fad941eb33",
                "factoryCode": "sha11111ww",
                "modelCode": "sha1a100",
                "label": "Device",
                "linkId": 21
            }, {
                "id": 158,
                "deviceId": "004901015da536e3e4b0bf772bd36773",
                "factoryCode": "dnc12332112",
                "modelCode": "00490101",
                "label": "Device",
                "linkId": 22
            }, {
                "id": 123,
                "deviceId": "0001011005dbd3acde4b00740880802d9",
                "factoryCode": "23534546",
                "modelCode": "000101100",
                "label": "Device",
                "linkId": 23
            }, {
                "id": 99,
                "deviceId": "000101485dd207aee4b03622287ebb9d",
                "factoryCode": "757869876876",
                "modelCode": "00010148",
                "label": "Device",
                "linkId": 24
            }, {
                "id": 4,
                "deviceId": "004101015dd64ea1e4b0c5015d3aebe2",
                "factoryCode": "123",
                "modelCode": "00410101",
                "label": "Device",
                "linkId": 25
            }, {
                "id": 142,
                "positionNumber": "001",
                "positionCode": "002",
                "label": "Position",
                "linkId": 26
            }, {
                "id": 44,
                "deviceId": "004901025d84c8bfe4b00b0c3273832a",
                "factoryCode": "1234132413241234",
                "modelCode": "00490102",
                "label": "Device",
                "linkId": 27
            }, {
                "id": 160,
                "deviceId": "004501035da43ba1e4b0940ae0681255",
                "factoryCode": "889900666666555",
                "modelCode": "00450103",
                "label": "Device",
                "linkId": 28
            }, {
                "id": 164,
                "deviceId": "005401015da67cd0e4b05e140edc73b1",
                "factoryCode": "201910161",
                "modelCode": "00540101",
                "label": "Device",
                "linkId": 29
            }, {
                "id": 96,
                "deviceId": "aa01a1005ddc9af2a973297a1cf341f3",
                "factoryCode": "001",
                "modelCode": "aa01a100",
                "label": "Device",
                "linkId": 30
            }, {
                "id": 151,
                "manufacturerCode": "aa01",
                "manufacturerName": "厂商aa01",
                "label": "Manufacturer",
                "linkId": 31
            }, {
                "id": 172,
                "iotInfrastructureName": "test20190619",
                "iotInfrastructureCode": "20190619",
                "factoryType": "Thingworx",
                "label": "IotInfrastructure",
                "linkId": 32
            }, {
                "id": 154,
                "deviceId": "aa01a1815d9feb526152de91705f9f6a",
                "factoryCode": "zyzy00781",
                "modelCode": "aa01a181",
                "label": "Device",
                "linkId": 33
            }, {
                "id": 153,
                "deviceId": "aa01a1815d9fec4f6152de91705f9f6b",
                "factoryCode": "zyzy0078234",
                "modelCode": "aa01a181",
                "label": "Device",
                "linkId": 34
            }, {
                "id": 159,
                "deviceId": "004901015da44155e4b02ff365d70baa",
                "factoryCode": "432141211",
                "modelCode": null,
                "label": "Device",
                "linkId": 35
            }, {
                "id": 103,
                "iotInfrastructureName": "测试816iot-center",
                "iotInfrastructureCode": "20190816",
                "factoryType": "IoT-Center",
                "label": "IotInfrastructure",
                "linkId": 36
            }, {
                "id": 60,
                "deviceId": "000101035ddc95a7e4b0fcf4c7a7dc3a",
                "factoryCode": "764563445",
                "modelCode": "00010103",
                "label": "Device",
                "linkId": 37
            }, {
                "id": 27,
                "name": "吾问无为谓",
                "employeeNumber": "142314",
                "phone": "13218787857",
                "label": "DeviceAdmin",
                "linkId": 38
            }, {
                "id": 28,
                "deviceId": "tui1a1005d5647ed270e07fad941eb33",
                "factoryCode": "yui11111ww",
                "modelCode": "tui1a100",
                "label": "Device",
                "linkId": 39
            }, {
                "id": 34,
                "deviceId": "000801025d0c75f98466a48347b9be1e",
                "factoryCode": "buchongceshi4",
                "modelCode": "00080102",
                "label": "Device",
                "linkId": 40
            }, {
                "id": 45,
                "manufacturerCode": "95664",
                "manufacturerName": "12",
                "label": "Manufacturer",
                "linkId": 41
            }, {
                "id": 29,
                "applicationName": "Test请勿删除此业务应用",
                "appId": "190708",
                "label": "Application",
                "linkId": 42
            }, {
                "id": 33,
                "deviceId": "aa01a1935d78cb6644527d9ccfdda354",
                "factoryCode": "qwertyuio",
                "modelCode": "5698",
                "label": "Device",
                "linkId": 43
            }, {
                "id": 157,
                "deviceId": "004101015da43846e4b02ff365d70ba8",
                "factoryCode": "wdnmddnc",
                "modelCode": "00410101",
                "label": "Device",
                "linkId": 44
            }, {
                "id": 143,
                "deviceId": "004901015dd648bae4b0c5015d3aebbf",
                "factoryCode": "dnb",
                "modelCode": "00490101",
                "label": "Device",
                "linkId": 45
            }, {
                "id": 133,
                "deviceId": "000101035dce3585e4b024fa72195ac6",
                "factoryCode": "20191115",
                "modelCode": "00010103",
                "label": "Device",
                "linkId": 46
            }, {
                "id": 126,
                "manufacturerCode": "0001",
                "manufacturerName": "测试厂商",
                "label": "Manufacturer",
                "linkId": 47
            }, {
                "id": 145,
                "positionNumber": "01",
                "positionCode": "02",
                "label": "Position",
                "linkId": 48
            }, {
                "id": 116,
                "name": "lili",
                "employeeNumber": "1123",
                "phone": "18236592287",
                "label": "DeviceAdmin",
                "linkId": 49
            }, {
                "id": 170,
                "name": "2423",
                "employeeNumber": "432432",
                "phone": "13213243567",
                "label": "DeviceAdmin",
                "linkId": 50
            }, {
                "id": 6,
                "deviceId": "004101015da3d9cee4b05637b9776da8",
                "factoryCode": "111111111111122222222333333334444444",
                "modelCode": "00410101",
                "label": "Device",
                "linkId": 51
            }, {
                "id": 35,
                "deviceId": "000101035da3e713e4b07ee3503d6bb8",
                "factoryCode": "235435",
                "modelCode": "00010103",
                "label": "Device",
                "linkId": 52
            }, {
                "id": 39,
                "name": "测试",
                "employeeNumber": "20191120",
                "phone": "13218787851",
                "label": "DeviceAdmin",
                "linkId": 53
            }, {
                "id": 161,
                "deviceId": "000101035da43615e4b0940ae0681254",
                "factoryCode": "9767456",
                "modelCode": "00010103",
                "label": "Device",
                "linkId": 54
            }, {
                "id": 155,
                "deviceId": "000101035dd6024de4b0b7a69b2099c6",
                "factoryCode": "7567435345334",
                "modelCode": "00010103",
                "label": "Device",
                "linkId": 55
            }, {
                "id": 15,
                "positionNumber": "21212",
                "positionCode": "1212",
                "label": "Position",
                "linkId": 56
            }, {
                "id": 114,
                "deviceId": "doo1a1005d5647ed270e07fad941eb33",
                "factoryCode": "doo11111ww",
                "modelCode": "aa01a100",
                "label": "Device",
                "linkId": 57
            }, {
                "id": 107,
                "manufacturerCode": "0021",
                "manufacturerName": "0619设备厂商测试",
                "label": "Manufacturer",
                "linkId": 58
            }, {
                "id": 110,
                "applicationName": "达西创意园",
                "appId": "000888",
                "label": "Application",
                "linkId": 59
            }, {
                "id": 127,
                "deviceId": "guo1a1005d5647ed270e07fad941eb33",
                "factoryCode": "guo11111ww",
                "modelCode": "guo1a100",
                "label": "Device",
                "linkId": 60
            }, {
                "id": 146,
                "manufacturerCode": "0049",
                "manufacturerName": "无锡爱玛有限公司",
                "label": "Manufacturer",
                "linkId": 61
            }, {
                "id": 171,
                "applicationName": "0129",
                "appId": "000111",
                "label": "Application",
                "linkId": 62
            }, {
                "id": 144,
                "positionNumber": "",
                "positionCode": "",
                "label": "Position",
                "linkId": 63
            }, {
                "id": 115,
                "deviceId": "aa01a1005d5647ed270e07fad941eb33",
                "factoryCode": "11111111ww",
                "modelCode": "aa01a100",
                "label": "Device",
                "linkId": 64
            }, {
                "id": 149,
                "iotInfrastructureName": "Oc测试平台",
                "iotInfrastructureCode": "Oc_Test",
                "factoryType": "OceanConnect",
                "label": "IotInfrastructure",
                "linkId": 65
            }, {
                "id": 85,
                "deviceId": "aa01a1005d79f79b7e86cb64421d5f2e",
                "factoryCode": "oc09121544",
                "modelCode": "aa01a100",
                "label": "Device",
                "linkId": 66
            }, {
                "id": 10,
                "manufacturerCode": "0041",
                "manufacturerName": "江南烟草厂",
                "label": "Manufacturer",
                "linkId": 67
            }, {
                "id": 148,
                "name": "测试",
                "employeeNumber": "20191118",
                "phone": "13218787857",
                "label": "DeviceAdmin",
                "linkId": 68
            }, {
                "id": 109,
                "deviceId": "aa01a2165dce164af140638d567c5c0c",
                "factoryCode": "1115factory001",
                "modelCode": "aa01a216",
                "label": "Device",
                "linkId": 69
            }, {
                "id": 31,
                "deviceId": "004501015d8493e1e4b07c14d91f6d0a",
                "factoryCode": "123312abcd",
                "modelCode": "00450101",
                "label": "Device",
                "linkId": 70
            }, {
                "id": 17,
                "deviceId": "004901015da91703e4b0311aeee1075a",
                "factoryCode": "4321412111",
                "modelCode": "00490101",
                "label": "Device",
                "linkId": 71
            }, {
                "id": 102,
                "deviceId": "000201025dd20c32e4b03622287ebb9e",
                "factoryCode": "2019111801",
                "modelCode": "00020102",
                "label": "Device",
                "linkId": 72
            }, {
                "id": 138,
                "manufacturerCode": "0048",
                "manufacturerName": "测试816",
                "label": "Manufacturer",
                "linkId": 73
            }, {
                "id": 0,
                "deviceId": "000101035dd7772fe4b052fe501d9f6f",
                "factoryCode": "test",
                "modelCode": "00010103",
                "label": "Device",
                "linkId": 74
            }, {
                "id": 167,
                "deviceId": "000101035dd3551de4b0502efc76fee0",
                "factoryCode": "20191119002",
                "modelCode": "00010103",
                "label": "Device",
                "linkId": 75
            }, {
                "id": 41,
                "deviceId": "000801025d0c7f1a8466e74289f900f0",
                "factoryCode": "buchongceshi5",
                "modelCode": "00080102",
                "label": "Device",
                "linkId": 76
            }, {
                "id": 141,
                "positionNumber": "987",
                "positionCode": "091",
                "label": "Position",
                "linkId": 77
            }]
        };
        this.renderGraph(data);
    },
    methods: {
        renderGraph(data) {
            let {links, nodes} = data;

            //关系分组
            setLinkGroup(links);

            //点击节点后弹出的灰色圆圈以及图标的定义，分为三组【1.删除、2.联系、3.解除位置锁定】
            let [removePath,remove_rect1,remove_rect2,remove_line1,remove_line2,remove_line3] = [null];
            let [unlockPath,unlock_path1,unlock_rect1,unlock_line1] = [null];
            let [hidePath,hide_path1,hide_path2,hide_path3,hide_path4,hide_circle1,hide_line1] = [null];
            let rightArc = d3.svg.arc().outerRadius(60).innerRadius(30).startAngle(0).endAngle(1.85);
            let leftArc = d3.svg.arc().outerRadius(60).innerRadius(30).startAngle(4.5).endAngle(6.23);
            let bottomArc = d3.svg.arc().outerRadius(60).innerRadius(30).startAngle(1.9).endAngle(4.45);

            d3.select("#graph").html('');

            const force = d3.layout.force()//layout将json格式转化为力学图可用的格式
                .nodes(nodes)//设定节点数组
                .links(links)//设定连线数组
                .linkDistance(150)//连接线长度
                .charge(-1500)//顶点的电荷数。该参数决定是排斥还是吸引，数值越小越互相排斥
                .on("tick", tick)//指时间间隔，隔一段时间刷新一次画面
                .start();//开始转换

            let zoom = d3.behavior.zoom()
                .scaleExtent([.4, 2])
                .on("zoom", zoomed);

            const svg = d3.select("#graph").append("svg")
                .attr("pointer-event", "all")
                .attr("preserveAspectRatio", "xMidYMid meet")//自适应容器大小
                .attr("viewBox", "0 0 1000 1000")
                .call(zoom);

            //设置连接线
            const edges_line = svg.append("g").selectAll(".edgepath")
                .data(force.links())
                .enter()
                .append("path")
                .attr("marker-end",  function (d, i) { return getMarkerArrow(i); })//根据箭头标记的id号标记箭头
                .style("stroke", '#9aaabf')
                .style("stroke-width", 1)//线条粗细
                .style("fill-opacity",0)
                .style("cursor","pointer")
                .attr("id", function (d, i) { return 'edgepath' + i; })
                .on("mouseover", function(d){ return getStrokeWidth(d); })
                .on("mouseout", function() { edges_line.style("stroke-width", 1) })
                .on('click', (d, i) => { deleteLine(d, i); });

            const edges_text = svg.append("g").selectAll(".edgetext")
                .data(links)
                .enter()
                .append("text")
                .style("pointer-events", "none")
                .attr("class","linetext")
                .attr('text-anchor', "middle")
                .attr("fill-opacity", 1)
                .style("cursor","pointer")
                .attr({'class': 'edgelabel', 'id': function (d, i) { return 'edgepath' + i; }, 'dx': 50, 'dy': 0, 'fill':'#9aaabf'});

            //设置线条上的文字
            edges_text.append('textPath')
                .attr('xlink:href', function (d, i) { return '#edgepath' + i })
                .attr("pointer-events", "none").attr("font-size", 9)
                .text(function (d) { return d.relation.relationship; });

            const circle_g = svg.selectAll("circle")
                .data(force.nodes())//表示使用force.nodes数据
                .enter()
                .append("g")
                .attr("class",function(node,i){ return "g_circle_" + i; })//标记circle的父节点
                .style("cursor","pointer")
                .call(drag()) //将当前选中的元素传到drag函数中，使顶点可以被拖动
                .on("click", (node, i) => {
                    if (d3.event.defaultPrevented) return;//阻止click事件和拖拽事件冲突
                    circleClick(node, i, this);
                })
                .on('mouseover', (node) => {
                    if (d3.event.defaultPrevented) return;
                    showNodeInfo(node, this);
                    // showCircleBorderOuterArc(node, i);
                });

            svg.on("dblclick.zoom", null);//取消svg和圆圈的双击放大事件（d3中默认开启7个事件，关闭防止与上面的双击事件冲突）
            circle_g.on("dblclick.zoom", null);

            //圆圈
            const circle = circle_g.append("circle")
                .style("stroke-width", "2px")
                .attr("r", 25)//设置圆圈半径
                .style("fill", function (node) { return getCircleColor(node); });

            let text = circle_g.append("text")
                .attr("dy", ".35em")
                .attr("text-anchor", "middle")//在圆圈中加上数据
                .style('fill', "#FFFFFF")
                .attr('x',function(d){ appendCircleText(d, this); });

            //圆圈的提示文字
            circle.append("svg:title").text(function(node) {
                switch (node.label) {
                    case 'Device': return node.factoryCode;
                    case 'Application': return node.applicationName;
                    case 'Position': return node.positionCode;
                    case 'Manufacturer': return node.manufacturerName;
                    case 'IotInfrastructure': return node.iotInfrastructureName;
                    case 'DeviceAdmin': return node.name;
                }
            });
            text.append("svg:title").text(function(node) {
                switch (node.label) {
                    case 'Device': return node.factoryCode;
                    case 'Application': return node.applicationName;
                    case 'Position': return node.positionCode;
                    case 'Manufacturer': return node.manufacturerName;
                    case 'IotInfrastructure': return node.iotInfrastructureName;
                    case 'DeviceAdmin': return node.name;
                }
            });

            function zoomed() {//svg下的g标签移动大小
                svg.selectAll("g").attr("transform", "translate("  +d3.event.translate + ")scale(" +d3.event.scale + ")");
            }

            function getMarkerArrow(i) {
                svg.append("defs").append("marker")   //箭头
                    .attr("id", "arrow"+i)
                    .attr("markerUnits","strokeWidth")//设置为strokeWidth箭头会随着线的粗细发生变化
                    .attr("markerUnits", "userSpaceOnUse")
                    .attr("markerWidth", 10)//标识的大小
                    .attr("markerHeight", 10)
                    .attr("viewBox", "0 -4 12 15")//坐标系的区域
                    .attr("refX", 0)//箭头坐标
                    .attr("refY", 0)
                    .attr("orient", 'auto')//绘制方向，可设定为：auto（自动确认方向）和 角度值
                    .append("svg:path")
                    .attr("stroke-width",1)//箭头宽度
                    .attr("d", "M0,-5L10,0L0,5")//箭头的路径
                    .attr('fill', 'rgba(0,0,0, 0.4)');//箭头颜色
                return "url(#arrow" + i + ")";
            }

            function getStrokeWidth(d) {
                edges_line.style("stroke-width", function (edge) {
                    return edge.relation.relationshipId === d.relation.relationshipId ? 3 : 1;
                });
            }

            function drag(){//拖拽函数
                return force.drag().on("dragstart",function(d){
                    d3.event.sourceEvent.stopPropagation(); //取消默认事件
                    d.fixed = true;//拖拽开始后设定被拖拽对象为固定
                });
            }

            function circleClick(node, i, _this) {
                //获取当前节点是否包含圆环
                let existedRing = svg.select('.g_circle_' + i).selectAll('.g_circle_path');
                //清除上个节点的圆圈以及图标
                svg.selectAll('.g_circle_path').remove();
                svg.selectAll('.remove_a').remove();
                svg.selectAll('.hide_a').remove();
                svg.selectAll('.unlock_a').remove();
                if(existedRing && existedRing[0].length === 0) {
                    //showCircleBorderOuterArc(node, i);
                    //绘制灰色可点击圆圈，分为三部分分别绘制
                    showRemove(node, i, _this);
                    showUnlock(node, i, _this);
                    showHide(node,i, _this);
                }
            }

            function getCircleColor(node) {
                let color = {
                    'Device': "#FF9D00",
                    'Position': "#C477E9",
                    'Work': '#67CAF4',
                    'Install': '#BCDD73',
                    'Application': '#DD1E9E',
                    'Manufacturer': '#DDBA9E',
                    'IotInfrastructure': '#6ca5dd',
                    'DeviceAdmin': '#50DD87',
                };//圆圈背景色
                return color[node.label] || '#C477E9';
            }

            function appendCircleText(d, _this) {
                let circleText = '';
                if(d.label === 'Device' && d.factoryCode) {
                    circleText = d.factoryCode;
                } else if(d.label === 'Position') {
                    circleText = d.positionCode;
                } else if (d.label === 'Application') {
                    circleText = d.applicationName;
                } else if (d.label === 'Manufacturer') {
                    circleText = d.manufacturerName;
                } else if (d.label === 'IotInfrastructure') {
                    circleText = d.iotInfrastructureName;
                } else if (d.label === 'DeviceAdmin') {
                    circleText = d.name;
                }
                //如果小于四个字符，不换行
                if(circleText && circleText.length > 4){
                    circleText = circleText.substring(0,4) + "...";
                    d3.select(_this).text(function(){return '';});
                }
                d3.select(_this).append('tspan').attr('x',0).attr('y',0).attr("font-size", 12)
                    .text(function(){ return circleText; });
            }

            function deleteLine(d, i) {
                alert('delete this '+ d + ',' + i);
            }

            function tick() {
                circle.attr("transform", transform1);//圆圈
                text.attr("transform", transform2);//顶点文字
                edges_line.attr('d', function (d) {
                    //绘制自己指向自己的路径
                    if(d.relation.isSelf) { return getNodeSelfPath(d) }
                    //绘制两个节点之间的路径
                    return getNodesLine(d);//曲线路径
                });

                // if(circleBorderOuterArcObj !== null) {
                //   circleBorderOuterArcObj.attr("transform", function (d){ return "translate("+d.x+","+d.y+")" });
                // }

                //绘制节点删除功能半圆环
                if(removePath !== null) {
                    removePath.attr("transform", function (d){ return "translate("+d.x+","+d.y+")" });

                    let r1 = null;
                    remove_rect1.attr('d',function(d) { r1 = d; })
                        .attr("x",r1.x + 33 + 6.75).attr("y",r1.y  - 36 + 9.75).attr("width",5).attr("height",3).attr("rx",1.5).attr("ry",1.5);

                    let r2 = null;
                    remove_rect2.attr('d',function(d) { r2 = d; })
                        .attr("x",r2.x + 30 + 6.75).attr("y",r2.y  - 33 + 9.75).attr("width",12).attr("height",14).attr("rx",1.5).attr("ry",1.5);

                    let l1 = null;
                    remove_line1.attr('d',function(d) { l1 = d; })
                        .attr("x1",l1.x + 28 + 6.75).attr("y1",l1.y - 33 + 9.75).attr("x2",l1.x + 45 + 6.75).attr("y2",l1.y - 33 + 9.75);

                    let l2 = null;
                    remove_line2.attr('d',function(d) { l2 = d; })
                        .attr("x1",l2.x + 34 + 6.75).attr("y1",l2.y - 30 + 9.75).attr("x2",l2.x + 34 + 6.75).attr("y2",l2.y - 23 + 9.75);

                    let l3 = null;
                    remove_line3.attr('d',function(d) { l3 = d; })
                        .attr("x1",l3.x + 38 + 6.75).attr("y1",l3.y - 30 + 9.75).attr("x2",l3.x + 38 + 6.75).attr("y2",l3.y - 23 + 9.75);
                }

                //绘制解除节点位置锁定半圆环
                if(unlockPath !== null) {
                    unlockPath.attr("transform", function (d){ return "translate("+d.x+","+d.y+")" });
                    unlock_path1.attr("transform", function (d){ return "translate("+ (d.x - 45) +","+ (d.y - 23) +")" });

                    let r1 = null;
                    unlock_rect1.attr('d',function(d) { r1 = d; })
                        .attr("x",r1.x  - 52 + 6.75).attr("y",r1.y - 30 + 9.75).attr("width",15).attr("height",12).attr("rx",1.5).attr("ry",1.5);

                    let l1 = null;
                    unlock_line1.attr('d',function(d) { l1 = d; })
                        .attr("x1",l1.x  - 52 + 15).attr("y1",l1.y  - 30 + 15).attr("x2",l1.x  - 52 +15).attr("y2",l1.y  - 30 + 18);
                }

                //绘制隐藏节点和关系半圆环
                if(hidePath !== null) {
                    hidePath.attr("transform", function (d){ return "translate("+d.x+","+d.y+")" });

                    hide_path1
                        .attr("d", function(d) {
                            return "M" + (d.x - 13) + "," + (d.y + 42) + "A15,15,0,0,1" + (d.x + 13) + "," + (d.y + 42)
                        });
                    hide_path2
                        .attr("d", function(d) {
                            return "M"+ (d.x - 12 + 10.4) + "," + (d.y + 34 + 10.937) + "A" + 3.749 + "," + 3.749 + ",0,1,1," + (d.x - 12 + 15.338) + "," + (d.y + 33 + 9)
                        });
                    hide_path3
                        .attr("d", function(d) {
                            return "M" + (d.x - 12) + "," + (d.y + 42) + "A20,20,0,0,0" + (d.x - 4) + "," + (d.y + 47)
                        });
                    hide_path4
                        .attr("d", function(d) {
                            return "M" + (d.x + 11) + "," + (d.y + 44) + "A20,20,0,0,0" + (d.x + 13) + "," + (d.y + 42)
                        });

                    let c1 = null;
                    hide_circle1.attr('d',function(d) { c1 = d; })
                        .attr("cx",c1.x - 12 + 17.15).attr("cy",c1.y + 33 + 17.25).attr("r",6);

                    let l1 = null;
                    hide_line1.attr('d',function(d) { l1 = d; })
                        .attr("x1",l1.x - 12 + 14.15).attr("y1",l1.y + 33 + 17.25).attr("x2",l1.x - 12 + 20.15).attr("y2",l1.y + 33 + 17.25);

                }

            }

            //设置圆圈和文字的坐标
            function transform1(d) {
                return "translate(" + d.x + "," + d.y + ")";
            }

            function transform2(d) {
                return "translate(" + (d.x) + "," + d.y + ")";
            }
            function showRemove(node, i, _this) {
                removePath = d3.select('.g_circle_'+ i).append("path").attr('class', 'g_circle_path')
                    .attr("transform", "translate(" + node.x + "," + node.y + ")").attr("d", rightArc)
                    .attr("fill", "rgb(210, 213, 218)")
                    .style("cursor","pointer")
                    .on("click", () => { removeNodeAndPath(node, _this); })
                    .on("mouseover", function(){ removePath.attr("fill", "rgb(185, 185, 185)") })
                    .on("mouseout", function() { removePath.attr("fill", "rgb(210, 213, 218)") });

                d3.select('.g_circle_'+ i).append("g").attr("class","remove_a")
                    .attr("transform", "translate(" + (node.x + 33) + "," + (node.y - 24) + ") scale(0.7)")
                    .append("defs").append("style")
                    .text(".remove_a{fill:none;stroke:#FFFFFF;stroke-linecap:round;stroke-linejoin:round;stroke-width:1.5px;}");

                removePath.append("title").attr("class","remove_a").text("Remove");
                remove_rect1 = d3.select('.g_circle_'+ i).append("rect").attr("class","remove_a").attr("x",node.x + 33 + 6.75).attr("y",node.y  - 36 + 9.75)
                    .attr("width",5).attr("height",3).attr("rx",1.5).attr("ry",1.5);
                remove_rect2 = d3.select('.g_circle_'+ i).append("rect").attr("class","remove_a").attr("x",node.x + 30 + 6.75).attr("y",node.y  - 33 + 9.75)
                    .attr("width",12).attr("height",14).attr("rx",1.5).attr("ry",1.5);
                remove_line1 = d3.select('.g_circle_'+ i).append("line").attr("class","remove_a").attr("x1",node.x + 28 + 6.75).attr("y1",node.y - 33 + 9.75).attr("x2",node.x + 45 + 6.75).attr("y2",node.y - 33 + 9.75);
                remove_line2 = d3.select('.g_circle_'+ i).append("line").attr("class","remove_a").attr("x1",node.x + 34 + 6.75).attr("y1",node.y - 30 + 9.75).attr("x2",node.x + 34 + 6.75).attr("y2",node.y - 23 + 9.75);
                remove_line3 = d3.select('.g_circle_'+ i).append("line").attr("class","remove_a").attr("x1",node.x + 38 + 6.75).attr("y1",node.y - 30 + 9.75).attr("x2",node.x + 38 + 6.75).attr("y2",node.y - 23 + 9.75);

                d3.selectAll(".remove_a").on("click", () => { removeNodeAndPath(node, _this); })
            }

            function showHide(node,i) {
                hidePath = d3.select('.g_circle_'+ i).append("path").attr('class', 'g_circle_path')
                    .attr("transform", "translate(" + node.x + "," + node.y + ")").attr("d", bottomArc)
                    .attr("fill", "rgb(210, 213, 218)")
                    .style("cursor","pointer")
                    .on("click", function(){ hideNodeAndLinks(node) })
                    .on("mouseover", function(){ hidePath.attr("fill", "rgb(185, 185, 185)") })
                    .on("mouseout", function() { hidePath.attr("fill", "rgb(210, 213, 218)") });

                d3.select('.g_circle_'+ i).append("g").attr("class","hide_a")
                    .attr("transform", "translate(" + (node.x - 8) + "," + (node.y + 38) + ") scale(0.7)")
                    .append("defs").append("style")
                    .text(".hide_a{fill:none;stroke:#FFFFFF;stroke-linecap:round;stroke-linejoin:round;stroke-width:1.5px;}");

                hidePath.append("title").attr("class","hide_a").text("Hide");

                hide_path1 = d3.select('.g_circle_'+ i).append("path").attr("class","hide_a")
                    .attr("d", function(d) {
                        return "M" + (d.x - 13) + "," + (d.y + 42) + "A15,15,0,0,1" + (d.x + 13) + "," + (d.y + 42)
                    });
                hide_path2 = d3.select('.g_circle_'+ i).append("path").attr("class","hide_a")
                    .attr("d", function(d) {
                        return "M"+ (d.x - 12 + 10.4) + "," + (d.y + 34 + 10.937) + "A" + 3.749 + "," +  3.749 + ",0,1,1," + (d.x - 12 + 15.338) + "," + (d.y + 33 + 9)
                    });
                hide_path3 = d3.select('.g_circle_'+ i).append("path").attr("class","hide_a")
                    .attr("d", function(d) {
                        return "M" + (d.x - 12) + "," + (d.y + 42) + "A20,20,0,0,0" + (d.x - 4) + "," + (d.y + 47)
                    });
                hide_path4 = d3.select('.g_circle_'+ i).append("path").attr("class","hide_a")
                    .attr("d", function(d) {
                        return "M" + (d.x + 11) + "," + (d.y + 44) + "A20,20,0,0,0" + (d.x + 13) + "," + (d.y + 42)
                    });
                hide_circle1 = d3.select('.g_circle_'+ i).append("circle").attr("class","hide_a").attr("cx",node.x - 12 + 17.15).attr("cy",node.y + 33 + 17.25).attr("r",6);
                hide_line1 = d3.select('.g_circle_'+ i).append("line").attr("class","hide_a").attr("x1",node.x - 12 + 14.15).attr("y1",node.y + 33 + 17.25).attr("x2",node.x - 12 + 20.15).attr("y2",node.y + 33 + 17.25);
                d3.selectAll(".hide_a").on("click", (d) => { hideNodeAndLinks(d); })
            }
            function showUnlock(node, i) {
                unlockPath = d3.select('.g_circle_'+ i).append("path").attr('class', 'g_circle_path')
                    .attr("transform", "translate(" + node.x + "," + node.y + ")").attr("d", leftArc)
                    .attr("fill", "rgb(210, 213, 218)").style("cursor","pointer")
                    .on("click", function(d){ unlockNodeFixed(d); })
                    .on("mouseover", function(){ unlockPath.attr("fill", "rgb(185, 185, 185)") })
                    .on("mouseout", function() { unlockPath.attr("fill", "rgb(210, 213, 218)") });

                d3.select('.g_circle_'+ i).append("g").attr("class","unlock_a")
                    .attr("transform", "translate(" + (node.x - 52) + "," + (node.y - 30) + ") scale(0.7)")
                    .append("defs").append("style")
                    .text(".unlock_a{fill:none;stroke:#FFFFFF;stroke-linecap:round;stroke-linejoin:round;stroke-width:1.5px;}");

                unlockPath.append("title").attr("class","unlock_a").text("Unlock");
                unlock_path1 = d3.select('.g_circle_'+ i).append("path").attr("class","unlock_a")
                    .attr("transform", "translate(" + (node.x - 45) + "," + (node.y - 23) + ")")
                    .attr("d", d3.svg.arc().outerRadius(5.3).innerRadius(5).startAngle(-1.8).endAngle(1.8))
                    .attr("fill", "#FFFFFF");

                unlock_rect1 = d3.select('.g_circle_'+ i).append("rect").attr("class","unlock_a").attr("x",node.x - 52 + 6.75).attr("y",node.y  - 30 + 9.75)
                    .attr("width",15).attr("height",12).attr("rx",1.5).attr("ry",1.5);
                unlock_line1 = d3.select('.g_circle_'+ i).append("line").attr("class","unlock_a").attr("x1",node.x  - 52 + 15).attr("y1",node.y - 30 + 15).attr("x2",node.x  - 52 + 15).attr("y2",node.y - 30 + 18);

                d3.selectAll(".unlock_a").on("click", (d) => { unlockNodeFixed(d); })

            }
            function hideNodeAndLinks(node) {
                d3.event.stopPropagation();
                circle_g.attr('node', function(n) {
                    if(n.id === node.id) {
                        d3.select(this).remove();
                    }
                });
                edges_line.attr('d', function(d) {
                    if(d.source.id === node.id || d.target.id === node.id) {
                        d3.select(this).remove();
                    }
                });
            }
            function removeNodeAndPath(node, _this){
                d3.event.stopPropagation();
                alert('delete this '+ node + ',' + _this );
            }
            function showNodeInfo(node, _this) {
                window.console.log(node);
                window.console.log(_this);

            }
            function unlockNodeFixed(d) {
                d3.event.stopPropagation();
                d3.select(this).classed("fixed", d.fixed = false);//解除节点位置锁定
                //清除上个节点的圆圈以及图标
                svg.selectAll('.g_circle_path').remove();
                svg.selectAll('.remove_a').remove();
                svg.selectAll('.hide_a').remove();
                svg.selectAll('.unlock_a').remove();
            }
        }

    }
}
</script>

<style>
  #graph {
    width: 100vw;
    height: 100vh;
  }
</style>
