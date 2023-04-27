# API Docs

## get collections owned by a specified wallet address.

---

#### api desc

| URL                                                                                                                                                                                           | request | version | status |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------ | :------ | :----- |
| [https://nftdataapi.chainsync.network/api/walletcollections/:chainId/:walletAddress](https://nftdataapi.chainsync.network/api/walletcollections/1/0xacdaEEb57ff6886fC8e203B9Dd4C2b241DF89b7a) | GET     | 1.0     | true   |

#### request params

| param name | type    | require | desc                                                                  | demo  |
| :--------- | :------ | :------ | :-------------------------------------------------------------------- | :---- |
| lastId     | Integer | false   | the last id for previous batch of collection                          | 381   |
| nonSynced  | Bool    | false   | only returns non synced collections                                   | true  |
| dstChainId | Integer | false   | only returns non synced collections based on this destnation chain id | 80001 |

#### return params

| param name | type    | desc        |
| :--------- | :------ | :---------- |
| errno      | Integer | 0：succeed  |
| data       | array   | collections |
| ...        | ...     | ...         |

#### return demo JSON

```json
{
  "errno": 0,
  "data": [
    {
      "id": 69,
      "wallet": "0xacdaEEb57ff6886fC8e203B9Dd4C2b241DF89b7a",
      "chainId": 1,
      "contract": "0x769272677fab02575e84945f03eca517acc544cc",
      "name": "Captainz",
      "symbol": "Captainz",
      "mirror": 1, // 0 normal collection 1 mirror collection 2 not support mirror collection
      "mirrorData": {
        "chain_id": 137, // origin collection chain Id
        "contract": "0x769272677fab02575e84945f03eca517acc544cc", // origin collection contract address
        "name": "Bored Ape Yacht Club", // origin name
        "symbol": "BAYC" //origin symbol
      }
    },
    {
      "id": 68,
      "wallet": "0xacdaEEb57ff6886fC8e203B9Dd4C2b241DF89b7a",
      "chainId": 1,
      "contract": "0x7828c811636ccf051993c1ec3157b0b732e55b23",
      "name": "DEGENERATE/REGENERATE",
      "symbol": "OBEYDG",
      "mirror": 0,
      "mirrorData": {}
    }
  ]
}
```

## get nfts owned by a specified wallet address.

---

#### api desc

| URL                                                                                                                                                                             | request | version | status |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :------ | :------ | :----- |
| [https://nftdataapi.chainsync.network/api/walletnfts/:chainId/:walletAddress](https://nftdataapi.chainsync.network/api/walletnfts/1/0xacdaEEb57ff6886fC8e203B9Dd4C2b241DF89b7a) | GET     | 1.0     | true   |

#### request params

| param name | type    | require | desc                                                           | demo  |
| :--------- | :------ | :------ | :------------------------------------------------------------- | :---- |
| lastId     | Integer | false   | the last id for previous batch of nfts                         | 381   |
| nonSynced  | Bool    | false   | only returns non synced nfts                                   | true  |
|collectionContract|String|false|only returns this collection's nfts|0xa0e8a9941d1e1bc2ed25f138be6b0b51c059b298|
| dstChainId | Integer | false   | returns mirrored and mirroredData field based on this destnation chain id | 80001 |

#### return params

| param name | type    | desc        |
| :--------- | :------ | :---------- |
| errno      | Integer | 0：succeed  |
| data       | array   | collections |
| ...        | ...     | ...         |

#### return demo JSON

```json
{
  "errno": 0,
  "data": [
    {
      "id": 146,
      "wallet": "0xacdaEEb57ff6886fC8e203B9Dd4C2b241DF89b7a",
      "chainId": 1,
      "contract": "0xa0e8a9941d1e1bc2ed25f138be6b0b51c059b298",
      "tokenId": "727",
      "metadata": {
        "name": "Canvas #727",
        "created_by": "FewoWorld",
        "description": "Canvas is a digital representation of a section of a real painted canvas from a Paint Party, given as a collectible reward to Paint Party attendees and Top Paint Holders. Each Canvas NFT is distinguishable by Paint Party and no two NFTs display the same fragment of canvas, making them all fully unique. The full physical canvases and an allocation of Canvas NFTs as reserves, will remain in the FewoWorld vault.",
        "image": "https://arweave.net/D3_TFFj3sx-yoWWpjXCalpNhmg14TcOsgs__EV4Tt3I",
        "image_url": "https://arweave.net/D3_TFFj3sx-yoWWpjXCalpNhmg14TcOsgs__EV4Tt3I",
        "image_details": {
          "bytes": 261131,
          "format": "JPEG",
          "sha256": "951adbbddb8a1f05bf72264dadbe5b2a865558aeffb24e98210816b2e7d21fe9",
          "width": 1080,
          "height": 1440
        },
        "animation": "https://arweave.net/Y1bTiwYRo3Asg7nodlM-droVoPDw2DcvSYnnVGNcTZE",
        "animation_url": "https://arweave.net/Y1bTiwYRo3Asg7nodlM-droVoPDw2DcvSYnnVGNcTZE",
        "animation_details": {
          "bytes": 24805756,
          "format": "MP4",
          "duration": 13,
          "sha256": "1d4fdb5f471c400e2b1c4e508341b1ff04478afa11544d3f968e6c8cbf3d9b24",
          "width": 1080,
          "height": 1440,
          "codecs": ["H.264", "AAC"]
        },
        "attributes": [
          {
            "trait_type": "Event",
            "value": "NYC 22"
          },
          {
            "trait_type": "Physical Canvas #",
            "value": 60
          },
          {
            "trait_type": "X Coordinate",
            "value": 3
          },
          {
            "trait_type": "Y Coordinate",
            "value": 7
          }
        ]
      },
      "mirror": 1, // 1: this nft is a mirror nft 0: normal nft 
      "mirrorData": {
        "chain_id": 137, // origin collection chain Id
        "contract": "0xa0e8a9941d1e1bc2ed25f138be6b0b51c059b298", // origin collection contract address
        "name": "Bored Ape Yacht Club", // origin name
        "symbol": "BAYC" // origin symbol
      },
      "mirrored": 0, // 1: this nft has syned mirror nft to destination chain Id 0: non syned 2 this nft not support for mirror
      "mirroredData": {} // if mirrored field returns 1 this field returns mirror nft data with same format like "mirrorData"
    }
  ]
}
```

## get chain confs

---

#### api desc

| URL                                                                                                                                                                             | request | version | status |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :------ | :------ | :----- |
| [https://nftdataapi.chainsync.network/api/mirrorchains](https://nftdataapi.chainsync.network/api/mirrorchains) | GET     | 1.0     | true   |

#### return params

| param name | type    | desc        |
| :--------- | :------ | :---------- |
| errno      | Integer | 0：succeed  |
| data       | array   | confs |
| ...        | ...     | ...         |

#### return demo JSON

```json
{
  "errno": 0,
  "data": [
    {
      chainId: 1, // chainId
      lastSyncBlock: 0,
      mirrorFactoryContract: "",
      mirrorFrom: 1,  // 1 means can mirror this chain's nft to other chains
      mirrorTo: 0
    },
    {
      chainId: 80001,
      lastSyncBlock: 34808145,
      mirrorFactoryContract: "0x4D19CFb55a6C96A857Ad2861f9cef9deDE0443E7", // mirror factory contract address when mirrorTo field is 1
      mirrorFrom: 0,
      mirrorTo: 1 // 1 means can mirror other chain's nft to this chain
    }
  ]
}
```
