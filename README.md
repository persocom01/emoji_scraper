# emoji-scraper

A simple piece of python code that extracts unique emojis on a webpage and saves them into a json file. Meant for use on https://www.unicode.org/emoji/charts/full-emoji-list.html to produce a list of emojis usable as a regex pattern.

Flag emojis are accounted for by adding a list of all two letter permutations of letter emojis to the extracted emojis to get a complete emoji list. Take note if attempting to use the code on a different webpage.

Alternative ways of getting a list of emojis include using emoji.UNICODE_EMOJI from the [emoji](https://github.com/alexandrevicenzi/emojis) library, but it returned an error when I used it in regex, captured a number of characters I did not consider emojis, and was thus not suitable for my purposes. That was how this mini 'project' was conceived.

## Requirements

* Python 3

This project was designed to only use python standard libraries.

## Installation

python has to be downloaded and installed.

* [python 3.8.2](https://www.python.org/downloads/)

## Usage

Edit emoji_scraper.py using any text editor. Paste the webpage into the "emoji_webpage" variable in the file before running it from command line or any IDE.

emojis.json is the result. It contains a list of emojis. You may just download the file if you are not concerned with new emoji updates.

### FAQ

> How do I use a list of emojis?

This code was written in order to get a regex pattern that can match all emojis. To get such a pattern, use:

```
with open(r'.\emojis.json') as f:
    emojis = json.load(f)

pattern = '|'.join(emojis)
```

> I get UnicodeEncodeError: 'charmap' codec can't encode character...

python is not running on utf-8 encoding on your computer. Append the following code to what you're running to fix the error:

```
import sys
import io

sys.stdout = io.TextIOWrapper(sys.stdout.detach(), encoding='utf-8')
sys.stderr = io.TextIOWrapper(sys.stderr.detach(), encoding='utf-8')
```

### Emojis

🚖🤴🌐🔈📭🕹🆖🕌🌴🌽🦲🐛🧑👻🥲🕞🎣💼🧸🚒💢🦻🍹🪵ç🕗🏄🛠👠🎀🍌🎪🕐🤥🐨🏭🍜🔛📲🪃🧫🛵😰🧱📐🖇🤵🍺😭📱📛🕸🍥󠁮🤚🕴🦖🧞😹🦘📹😈🏙🩲👈⌚🧢🦠☕💷🕎🥵😪👙👥🗑↩📣🏞🥛🦪🚠🦎🕯💓➕🎨🍾🔞🦧📥💏⏹🎾🆘🎰🏔💥✈📄🦑🥪🥂🥥📍🤏🍣🥿📡👽☠🩺😑🎇🐗🔪🎞🙄😶🎛🐣🌟🍫🏂🈚🚵🀄󠁳🔟🔳🐪✝🍭🚥☺🆒🚳🐏🛰🐦🟧🍿🌼🪳🌱🏥😒🛌🟢🐔🈺👟🪆í❓🛶🎢🥱🎹🈲🦿🛍🍇💙🪞🥧🤛🫒🪜😝🍃🎄♨🎓🧲👭🌅🚓🤌😇🙈🙂🍞🛢➖🍆🦄🚗🥩↕🏅📁🉐🤡🤞🐳✍🆕⬜🔙🧽🍛➰🌲🎊🐑🚐🛷👛🛃🥶😆🖱👺🆎🌌⏯🧕🛳🏚🍑🪅❕🪨⌛🥈🙊🌧💁🦁🏜🗽🚷🕙📎🚪🎽😱♓👨🐘😤🕤🎳🐙📢😁🗝⭕🥳🐮😼🎠🥷󠁢◀🛗🧒🔆🚬👎🏮♾🌄📪🍂📴🦴🔜🔥🈯🍄🤎🦝🥢✊📶🔎🕳🌖🉑🌹🍗💶💅🚄😖🐁👧👂🏠🤤🔍󠁴‼🍮💛🧳🎡🎈🕊🎲🟩🚂😏📺🥭🪗😜🎩🌬🚞⏸▪✴🏨🧪🏩🔦🈳🥌😀🗞💃🖕🛤🚉🐲🧠🏡🏪🕚📼🍒⏭🦂💋🐺😞👢🏗🧬🤜🥟🪖🐫…🛄🔅💜🦜➗💲⬅💧🎯🚸◻🤼🌦👒🍘🐞♍💱🙉🐶🚯🏯🟥👡🖨🐀🈷🎮🦅🕥❎🐋👴💒⬆⚪🔊🎒⏏🖲⏫🙅🕍📮🧍🆗№😧⏳📟👱🕠🏐❌🍧🧈🥝🧶🍚🦟☹🤽®👸📞🏉👼⊛😲💔🫐👉🌊🆙🟫📊🚑🔰🏝🧏🎏😯🥻☁🧚🏬🆓🔓👿🪐🚌🪂🖼👫🐍🧟🧰😮🧭🌕☀🦱🍎💬🐆🥞⚠🗒🤿🥊🦽ñ🛋👩🈶🍽🙁🅱♉🏷🦈🧎🌸🤐🦗🧨🍋♈🦀🌝📧🌘🧊👕🍔🔵📗🚏🥽🖥👗🦷🤓🎭👑🧦❄👁🌆🪢🕕🧁🪘🦺💭🚎🌗🦉📉🤑🏫🎫⛴🏤🛼😸😍🌃👹⚒📙☣🪁🍏🐉🛑☯🦋🦍📏🕜🔏🤰é🤗👪🐱🤷🤾󠁣⏲💺♐⛎🟣👅🍴🐓🥅🙋⌨🎵✋⛩🫀↗🐠🎷😐👘♎👰🔑🍢😻📘🛅🍝💘🏟🐜🦛😔🥮🧴📋☸⛸🛣🪠💠🤙🦞☢📳💈🥠🐽🌮🥯🐤♒🎼▶📸🧝⚽👯🕓🌑ℹ♦⛄👇🪥☘🛻⬛🌞🦇☝🛐🚝🧄🈁🏺⏪🤔🌛🌈😽🐬🐕🛂👤🧮🌨🥄🦃🌔😠🚔📃😳🐾⛺💩🧯🆚🥓🏹🕖⁉🪝🥣🖤🤪🔩😚🚊🍐🖐🪧↖🗜🍉📓🛎😟🍈📈🏕📒🏖👖💿👋👀😷🎃🟠🕛🚶🥏😣⚰🌯💴🥜🔯🚤🎐🧅󠁬♊🌇◾🐢🚿😵🎅🍰🪰🦊👆🛸📯🌠❗🚘🔝😬🔌🎎🥑🤖🗡🦮💎✅🫂🚧🪄🚩🤳🦒👍🏆🥡🦥🥋🎤🦰📽😙🍠⛵🧔🤝🐒🧂🧥🪚📠💂🥫🦨😅🟪🟦🙌™🎺📤👚🗿✡🎟🧩☦🐐🕋📻🍓💹🖌⏰🍙🌡〽😂💳🛺🥴⃣🕣🕶👷🏍⛓🍬🔣🪓💵💽🛏💟⚗💦🏦😗🏃🤢🛫🦢🔮🎍☑🌿😡🐃🎬🔀💫😫⤵🅾🎸🙏🦾📌↙🫑🥐🙎🧖🛹⛏🤘🙆🧆🚫📷💰⛪🔚🪒🏳💞🥖🌪📫😓🤺⛅🦸📖🔫❇💌🧇🧓🍅🔼⚔🏇☂󠁿👳🚟🪣🛡🛴♌🤹🦳🥒🤶🚍🍪🥤🥸🗯💐🍵📚😨㊗😊🌰⚫🔘🔨🦆🧋🖊🧼🏑🚈😎🔒🧿🏛♂🔹🥁🔧📰🈂🦭🗄📿💇🐵🦦🎖🎗🟨🌩👾😾🅿🗻🔸💤🖍🚜🦬🏵🧉📨▫🛒🤦🦓📑❤♿⏬🧤🗳😃💚⚛🈹⤴Å🏌🗺🚱🪔🌭🌉🎚💑🌓🚮🧾👐🍨🤍🕝🥎🐸💍🚋🔱🌍🤩➡🍟🚲↔💄🥕🎴😘🦙🚦🥔🚰✌🗾🧙👮🦡🕉👓🥰🦶📝🔬🦤😛🧣⚜🈵⏺🆑🌀🧃🗂🦔⬇🪟🥦🕺🍶😢🕢©🕷⚖🌻🎦🥀💣🍀🈸🍊🫁🐈🌥🚾🎿🤧⏱⛲🐅🕰🧧🐝🥃🪴🪦🔇👶🏰🚹🍷🐴🏊🤬🌁🐻🌋🐡🦹🌫🙀🪑🪡🏒🍤📆✨🎱✉🎌⛳🏣🐖📬🤭‍🛥🪛😴🌂🐩♥🤟🐂♠🥗🤯🧗🚣🟡⚱🏀😋💯👊📔🔁🍻❔🛀🎶🩸🔺🚴🚙🕒🍍🤕🦌👌🌚🦵🚨🦕🍯🥚🔷⚙🛁🥉🎑🔃🥺💪󠁧🚡🛕🕘⛔🌳🔲🤒🌒🧛🪤🏸💡🧘🍖🦐🥍🍦󠁷🪀🐭📦☮🤨🧹🎉👞🏧🌶🃏🌏↪🐟⭐♟🧀🔻🥙🍱🐹🥼🅰🎻🎁🏁🔐🐇🌎◼🎙💆🚼⚕🦼👃⛹💗️🏋💻👜🚀💮💸📵🫕ô🏢♣🖋🥾🩹🔔🔄📅🗨🔴🪶🍡🍩🌜📩🤲🤠󠁥⛷◽🍳💊🗣👬🚢🍸☔🔽🕧✂🐯㊙🛩☃🔠🕡🧐⛈🧺🟤🤮⛰🚭➿🔢🏈🗓📂⏩🚻⛽💖🦣🐰🚃👣🧵🦯🌵✖🕵✏🔋🛖🐼👲🪕🐷🥬🚆💕🤸🥇🎧🧷🚽Ⓜ⏮🎆👄🙍🧜😿🏏🌤🌷⚡🦫⚧🐧📕🚅🎥🧡🪱😉🪲🦏🏴🤫🤣🧻🈴🚕❣🍕🔤🩱☎⚓🏘🔡🍲🕔💀☄🐚😥♋🔶🗼⚾📇🔭🩳🔖🚁↘🎋🔗⛑🚛🕦〰🦩🔕🤱🐎🗃👔🙇👏🌺🍁🐄☪🎂🛬🕟🩴🏎✔🫔🥨🏓💉👝🚇🐌🐿🪙🩰🚚✒⛱🚺😺😌📀😩💝🫓👵🫖♀🔂♑💨ã🍼😄🔉🦚🐊🕑👦🐥♻💾♏📜🥘🙃🖖✳😕🌙🌾😦🆔🇶🇨🇶🇩🇶🇦🇶🇹🇶🇺🇶🇪🇶🇬🇶🇰🇶🇽🇶🇭🇶🇲🇶🇷🇶🇴🇶🇿🇶🇳🇶🇸🇶🇮🇶🇻🇶🇧🇶🇼🇶🇱🇶🇯🇶🇫🇶🇵🇶🇾🇨🇶🇨🇩🇨🇦🇨🇹🇨🇺🇨🇪🇨🇬🇨🇰🇨🇽🇨🇭🇨🇲🇨🇷🇨🇴🇨🇿🇨🇳🇨🇸🇨🇮🇨🇻🇨🇧🇨🇼🇨🇱🇨🇯🇨🇫🇨🇵🇨🇾🇩🇶🇩🇨🇩🇦🇩🇹🇩🇺🇩🇪🇩🇬🇩🇰🇩🇽🇩🇭🇩🇲🇩🇷🇩🇴🇩🇿🇩🇳🇩🇸🇩🇮🇩🇻🇩🇧🇩🇼🇩🇱🇩🇯🇩🇫🇩🇵🇩🇾🇦🇶🇦🇨🇦🇩🇦🇹🇦🇺🇦🇪🇦🇬🇦🇰🇦🇽🇦🇭🇦🇲🇦🇷🇦🇴🇦🇿🇦🇳🇦🇸🇦🇮🇦🇻🇦🇧🇦🇼🇦🇱🇦🇯🇦🇫🇦🇵🇦🇾🇹🇶🇹🇨🇹🇩🇹🇦🇹🇺🇹🇪🇹🇬🇹🇰🇹🇽🇹🇭🇹🇲🇹🇷🇹🇴🇹🇿🇹🇳🇹🇸🇹🇮🇹🇻🇹🇧🇹🇼🇹🇱🇹🇯🇹🇫🇹🇵🇹🇾🇺🇶🇺🇨🇺🇩🇺🇦🇺🇹🇺🇪🇺🇬🇺🇰🇺🇽🇺🇭🇺🇲🇺🇷🇺🇴🇺🇿🇺🇳🇺🇸🇺🇮🇺🇻🇺🇧🇺🇼🇺🇱🇺🇯🇺🇫🇺🇵🇺🇾🇪🇶🇪🇨🇪🇩🇪🇦🇪🇹🇪🇺🇪🇬🇪🇰🇪🇽🇪🇭🇪🇲🇪🇷🇪🇴🇪🇿🇪🇳🇪🇸🇪🇮🇪🇻🇪🇧🇪🇼🇪🇱🇪🇯🇪🇫🇪🇵🇪🇾🇬🇶🇬🇨🇬🇩🇬🇦🇬🇹🇬🇺🇬🇪🇬🇰🇬🇽🇬🇭🇬🇲🇬🇷🇬🇴🇬🇿🇬🇳🇬🇸🇬🇮🇬🇻🇬🇧🇬🇼🇬🇱🇬🇯🇬🇫🇬🇵🇬🇾🇰🇶🇰🇨🇰🇩🇰🇦🇰🇹🇰🇺🇰🇪🇰🇬🇰🇽🇰🇭🇰🇲🇰🇷🇰🇴🇰🇿🇰🇳🇰🇸🇰🇮🇰🇻🇰🇧🇰🇼🇰🇱🇰🇯🇰🇫🇰🇵🇰🇾🇽🇶🇽🇨🇽🇩🇽🇦🇽🇹🇽🇺🇽🇪🇽🇬🇽🇰🇽🇭🇽🇲🇽🇷🇽🇴🇽🇿🇽🇳🇽🇸🇽🇮🇽🇻🇽🇧🇽🇼🇽🇱🇽🇯🇽🇫🇽🇵🇽🇾🇭🇶🇭🇨🇭🇩🇭🇦🇭🇹🇭🇺🇭🇪🇭🇬🇭🇰🇭🇽🇭🇲🇭🇷🇭🇴🇭🇿🇭🇳🇭🇸🇭🇮🇭🇻🇭🇧🇭🇼🇭🇱🇭🇯🇭🇫🇭🇵🇭🇾🇲🇶🇲🇨🇲🇩🇲🇦🇲🇹🇲🇺🇲🇪🇲🇬🇲🇰🇲🇽🇲🇭🇲🇷🇲🇴🇲🇿🇲🇳🇲🇸🇲🇮🇲🇻🇲🇧🇲🇼🇲🇱🇲🇯🇲🇫🇲🇵🇲🇾🇷🇶🇷🇨🇷🇩🇷🇦🇷🇹🇷🇺🇷🇪🇷🇬🇷🇰🇷🇽🇷🇭🇷🇲🇷🇴🇷🇿🇷🇳🇷🇸🇷🇮🇷🇻🇷🇧🇷🇼🇷🇱🇷🇯🇷🇫🇷🇵🇷🇾🇴🇶🇴🇨🇴🇩🇴🇦🇴🇹🇴🇺🇴🇪🇴🇬🇴🇰🇴🇽🇴🇭🇴🇲🇴🇷🇴🇿🇴🇳🇴🇸🇴🇮🇴🇻🇴🇧🇴🇼🇴🇱🇴🇯🇴🇫🇴🇵🇴🇾🇿🇶🇿🇨🇿🇩🇿🇦🇿🇹🇿🇺🇿🇪🇿🇬🇿🇰🇿🇽🇿🇭🇿🇲🇿🇷🇿🇴🇿🇳🇿🇸🇿🇮🇿🇻🇿🇧🇿🇼🇿🇱🇿🇯🇿🇫🇿🇵🇿🇾🇳🇶🇳🇨🇳🇩🇳🇦🇳🇹🇳🇺🇳🇪🇳🇬🇳🇰🇳🇽🇳🇭🇳🇲🇳🇷🇳🇴🇳🇿🇳🇸🇳🇮🇳🇻🇳🇧🇳🇼🇳🇱🇳🇯🇳🇫🇳🇵🇳🇾🇸🇶🇸🇨🇸🇩🇸🇦🇸🇹🇸🇺🇸🇪🇸🇬🇸🇰🇸🇽🇸🇭🇸🇲🇸🇷🇸🇴🇸🇿🇸🇳🇸🇮🇸🇻🇸🇧🇸🇼🇸🇱🇸🇯🇸🇫🇸🇵🇸🇾🇮🇶🇮🇨🇮🇩🇮🇦🇮🇹🇮🇺🇮🇪🇮🇬🇮🇰🇮🇽🇮🇭🇮🇲🇮🇷🇮🇴🇮🇿🇮🇳🇮🇸🇮🇻🇮🇧🇮🇼🇮🇱🇮🇯🇮🇫🇮🇵🇮🇾🇻🇶🇻🇨🇻🇩🇻🇦🇻🇹🇻🇺🇻🇪🇻🇬🇻🇰🇻🇽🇻🇭🇻🇲🇻🇷🇻🇴🇻🇿🇻🇳🇻🇸🇻🇮🇻🇧🇻🇼🇻🇱🇻🇯🇻🇫🇻🇵🇻🇾🇧🇶🇧🇨🇧🇩🇧🇦🇧🇹🇧🇺🇧🇪🇧🇬🇧🇰🇧🇽🇧🇭🇧🇲🇧🇷🇧🇴🇧🇿🇧🇳🇧🇸🇧🇮🇧🇻🇧🇼🇧🇱🇧🇯🇧🇫🇧🇵🇧🇾🇼🇶🇼🇨🇼🇩🇼🇦🇼🇹🇼🇺🇼🇪🇼🇬🇼🇰🇼🇽🇼🇭🇼🇲🇼🇷🇼🇴🇼🇿🇼🇳🇼🇸🇼🇮🇼🇻🇼🇧🇼🇱🇼🇯🇼🇫🇼🇵🇼🇾🇱🇶🇱🇨🇱🇩🇱🇦🇱🇹🇱🇺🇱🇪🇱🇬🇱🇰🇱🇽🇱🇭🇱🇲🇱🇷🇱🇴🇱🇿🇱🇳🇱🇸🇱🇮🇱🇻🇱🇧🇱🇼🇱🇯🇱🇫🇱🇵🇱🇾🇯🇶🇯🇨🇯🇩🇯🇦🇯🇹🇯🇺🇯🇪🇯🇬🇯🇰🇯🇽🇯🇭🇯🇲🇯🇷🇯🇴🇯🇿🇯🇳🇯🇸🇯🇮🇯🇻🇯🇧🇯🇼🇯🇱🇯🇫🇯🇵🇯🇾🇫🇶🇫🇨🇫🇩🇫🇦🇫🇹🇫🇺🇫🇪🇫🇬🇫🇰🇫🇽🇫🇭🇫🇲🇫🇷🇫🇴🇫🇿🇫🇳🇫🇸🇫🇮🇫🇻🇫🇧🇫🇼🇫🇱🇫🇯🇫🇵🇫🇾🇵🇶🇵🇨🇵🇩🇵🇦🇵🇹🇵🇺🇵🇪🇵🇬🇵🇰🇵🇽🇵🇭🇵🇲🇵🇷🇵🇴🇵🇿🇵🇳🇵🇸🇵🇮🇵🇻🇵🇧🇵🇼🇵🇱🇵🇯🇵🇫🇵🇾🇾🇶🇾🇨🇾🇩🇾🇦🇾🇹🇾🇺🇾🇪🇾🇬🇾🇰🇾🇽🇾🇭🇾🇲🇾🇷🇾🇴🇾🇿🇾🇳🇾🇸🇾🇮🇾🇻🇾🇧🇾🇼🇾🇱🇾🇯🇾🇫🇾🇵

## Current status and issues

### Status

This is the only version until I have free time and decide to add more features:

1. Adding code that automatically scrapes the website instead of needing manual copy and paste.
2. Creating an emoji dictionary.

### Known issues

1. The approach to accounting for flag emojis results in non-existant letter permutations being added to the emoji list.
2. Does not account for skin tone variations of emojis.

## License

MIT License - see [LICENSE.md](LICENSE.md).
