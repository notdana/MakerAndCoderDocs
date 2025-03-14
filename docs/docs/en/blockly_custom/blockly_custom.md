# UIFlow Blockly Custom

## Block Editor

Click on the `Custom` option in the block list > `Create` to open the online Block editor.

<img src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/blockly_custom/blockly_custom_01.jpg" width="70%">

## Block Create

Click on the `Add` option below `Parameter` to add a program attribute, enter the name to be displayed by the block and select the attribute type, and enter the code to be included in the custom block in the `Block Code` box.

<img src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/blockly_custom/blockly_custom_02.jpg" width="70%">

To create a new block, we need to provide.

- `1:Group name`: the name of the group in which the custom block will be placed

- `2:Block color`: the exterior color of the block

- `3:Block tag`: only letters, numbers, underscores are allowed

- `4:Block type`: defines the type of the block as `Value`, or `Execute`.

- `5:Number of blocks`: ability to add multiple blocks at the same time and save them to a single `.m5b` file at the same time.

When the attribute type of a custom block has a constant or variable input, we can obtain these values in code and perform further processing and arithmetic.

Example: Select the property type as `String` (string input), then in the program, if we want to get the input string, we only need to use `${Parameter name}` in the code, that is, `${show_word}`, and it should be noted that when there is a space in the name of the block, you need to replace the space with an underscore in the code to get the input string. Use `_` underscores to replace spaces.

When you have finished editing the program, click `Download` to save it. Later, you can click `Open .m5b` again to open the saved customized block file (.m5b) for modification.

## Import Block

Click on `Custom` option > `Open` in the block list, import the block file (.m5b) created in the previous step, and the imported custom block will be included in the Custom option.

<img src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/blockly_custom/blockly_custom_03.jpg" width="70%">

<img src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/blockly_custom/blockly_custom_04.jpg" width="70%">


