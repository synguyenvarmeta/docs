# Metadata Structure

| Field           | Description                                                                                                                                                                                                                                 |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `image`         | This is the URL to the image of the item. Can be just about any type of image, and can be IPFS URLs or paths. We recommend using a 350 x 350 image.                                                                                         |
| `external_url`  | This is the URL that will appear below the asset's image on NFTify and will allow users to leave NFTify and view the item on your site.                                                                                                      |
| `description`   | A human readable description of the item. Markdown is supported.                                                                                                                                                                             |
| `name`          | Name of the item.                                                                                                                                                                                                                            |
| `attributes`    | These are the attributes for the item, which will show up on the page for the item. (see below)                                                                                                                                               |
| `animation_url` | A URL to a multi-media attachment for the item. The file extensions GLB, WEBM, MP4, and OGG are supported, along with the audio-only extensions MP3 and WAV. `animation_url` also supports HTML pages, allowing you to build rich experiences and interactive NFTs using JavaScript canvas, WebGL, and more. Scripts and relative paths within the HTML page are now supported. However, access to browser extensions is not supported. |
| `youtube_url`   | A URL to a YouTube video (only used if `animation_url` is not provided).                                                                                                                                                                     |

# Attributes

| Display Type        | Description                                                                                               | Example                                                                                               |
|---------------------|-----------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------|
| `boost_number`      | Indicates a numerical boost to the item, such as an increase in power or speed.                           | ```json { "display_type": "boost_number", "trait_type": "Aqua Power", "value": 40 } ```               |
| `boost_percentage`  | Indicates a percentage increase in a certain characteristic, amplifying the item's abilities proportionally.| ```json { "display_type": "boost_percentage", "trait_type": "Stamina Increase", "value": 10 } ```     |
| `number`            | Represents a simple number, used for levels, generation numbers, or other numeric attributes.             | ```json { "display_type": "number", "trait_type": "Generation", "value": 2 } ```                      |
| `date`              | Represents a date as a Unix timestamp (seconds since the Unix epoch).                                     | ```json { "display_type": "date", "trait_type": "Birthday", "value": 1618953600 } ```                 |
| `null`              | Represents a default view                                                                                 | ```json { "trait_type": "Birthday", "value": 1618953600 } ```                                         |

**Description of `trait_type` and `value`:**

- `trait_type`: Describes the trait category or characteristic.
- `value`: Describes the specific value of the trait.

**Detail of `trait_type` in sushi game:**

| Trait Type            | Value             | Display Type        | Description                                                      |
|-----------------------|-------------------|---------------------|------------------------------------------------------------------|
| Character Type        | Sushi             |                     | The general type of the character.                               |
| Sushi Type            | Nigiri Supreme    |                     | Specifies the kind of sushi.                                     |
| Engagement Level      | Paid NFT User     |                     | Indicates if the user is a free player or a paid NFT user.       |
| Play-and-Earn         | Enabled           |                     | Indicates whether the character is eligible for play-and-earn rewards. |
| Special Ability       | Swift Dash        |                     | The unique ability the character possesses.                      |
| Properties            | Tough             |                     | General characteristics of the sushi character.                  |
| Size                  | Medium            |                     | The physical size of the sushi character.                        |
| Ingredient            | Rice And Eggs     |                     | Main ingredients of the sushi character.                         |
| Speed                 | Moderate          |                     | The movement speed of the character.                             |
| Points                | 22                | number              | The initial points associated with the character.                |
| Power                 | 3                 | boost_number        | The boost number for the character’s power.                      |
| Attack Power          | 20%               | boost_percentage    | Percentage increase in attack power.                             |
| Obstacle Resistance   | 20%               | boost_percentage    | Percentage resistance to obstacles.                              |
| Birthday              | 1546360800 (Unix Timestamp) | date | The creation date of the NFT in Unix timestamp format.          |


# Example Metadata JSON

```json
{
  "name": "Sushi Character - Nigiri Supreme",
  "description": "Nigiri Supreme is a top-tier sushi character in Sushi Farm, featuring a delicate balance of rice and fresh fish. As a Paid NFT User, this character offers exclusive benefits like Play-and-Earn rewards, future customization options, and access to upcoming exclusive tournaments.",
  "image": "https://www.sushifarm.io/_next/image?url=%2F_next%2Fstatic%2Fmedia%2Fsalmon-roll.b431adb5.png&w=828&q=75",
  "external_url": "https://www.sushifarm.io/",
  "animation_url":"https://www.sushifarm.io/animation_url",
  "attributes": [
     {
      "trait_type": "Character Type",
      "value": "Sushi"
    },
    {
      "trait_type": "Sushi Type",
      "value": "Nigiri Supreme"
    },
    {
      "trait_type": "Engagement Level",
      "value": "Paid NFT User"
    },
    {
      "trait_type": "Play-and-Earn",
      "value": "Enabled"
    },
    {
      "trait_type": "Special Ability",
      "value": "Swift Dash"
    },
    {
      "trait_type": "Properties",
      "value": "Tough"
    },
    {
      "trait_type": "Size",
      "value": "Medium"
    },
    {
      "trait_type": "Ingredient",
      "value": "Rice And Eggs"
    },
    {
      "trait_type": "Speed",
      "value": "Moderate"
    },
    {
      "display_type": "number",
      "trait_type": "Points",
      "value": 22
    },
    {
      "display_type": "boost_number",
      "trait_type": "Power",
      "value": 3
    },
    {
      "display_type": "boost_percentage",
      "trait_type": "Attack power",
      "value": 20
    },
    {
      "display_type": "boost_percentage",
      "trait_type": "Obstacle Resistance",
      "value": 20
    },
    {
      "display_type": "date",
      "trait_type": "birthday",
      "value": 1546360800
    }
  ]
}


```

For more details, refer to the official documentation on [NFTify Metadata Standards](https://support.nftify.network/hc/en-us/articles/4409618795417-Metadata-Standards) and [OpenSea Metadata Standards](https://docs.opensea.io/docs/metadata-standards).





