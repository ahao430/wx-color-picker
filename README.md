# wx-color-picker
小程序颜色选择器
基于https://github.com/KirisakiAria/we-color-picker
感觉这个选择器的使用方法不太方便，对其进行了封装，不直接在页面渲染多个实例，而是做成公用一个弹窗选择。
接收show和color两个参数，打开后根据传入color初始化定位，可鼠标选择颜色，也可手动输入。点击确定传递选中颜色给页面。
使用方法

````wxml
  <view class="btn">选择颜色</view>
  
  <color-picker show="{{isColorPickerShow}}" color="{{curColor}}" catch:close="handleHideColorPicker" catch:change="onColorSelect"> </color-picker>
````
````js
  Page({
  data: {
    isColorPickerShow: false,
    curColor: '',
  },

  // 设置颜色
  handleSelectColor (e) {
    this.setData({
      curColor: e.currentTarget.dataset.color,
      isColorPickerShow: true,
    })
  },
  handleHideColorPicker () {
    this.setData({
      isColorPickerShow: false,
    })
  },
  onColorSelect () {
    this.setData({
      isColorPickerShow: false,
    })
  },
})

````
