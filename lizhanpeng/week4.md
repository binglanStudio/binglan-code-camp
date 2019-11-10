
   index.js：

     Page({
     data: {
    input: '',
    todos: [],
    logs: [],
    num:0
    },
    //储存list与logs本地
    save:function(){
      qq.setStorageSync('list', this.data.todos)
      qq.setStorageSync('logs', this.data.logs)
    },
    //加载本地的list与logs
     load:function(){
     var todos = qq.getStorageInfoSync('list')
     if(todos){
        var num = todos.filter(function (item) {
        return
        })
       this.setData({ todos: todos,num:num})
      }
     var logs = qq.getStorageInfoSync('logs')
    if(logs){
       this.setData({ logs: logs})
    }
    },
     //添加list
      addlist:function(){
     if (!this.data.input) {
      return
     }
      var todos = this.data.todos
      todos.push({name: this.data.input})
      var logs = this.data.logs
      logs.push({name: this.data.input})
      this.setData({
      input: '',
      todos: todos,
      logs: logs,
      num: this.data.num+1,
     })
      this.save()
      },
       inputChange: function (e) {
     this.setData({ input: e.detail.value })
     },
     //删除操作
      deletelist:function (e) {
     var index = e.currentTarget.dataset.index
     var todos = this.data.todos
     var remove = todos.splice(index, 1)[0]
     var logs = this.data.logs
     logs.push({name: remove.name })
     this.setData({
      todos: todos,
      num: this.data.num-1,
      logs: logs
     })
      this.save()
     }
      })

index.qml:

     <view class="container">
    <view class="header">
    <input class="input"  value="{{ input }}" placeholder="添加你的list"            auto-focus bindconfirm="addlist" bindinput="inputChange"/>
    </view>
     <view>
    <view class="list">
    <view class="item" qq:for="{{ todos }}" >
     <icon  class="remove" type="clear" size="13" catchtap="deletelist" data-index="{{ index }}"/>
        <text class="name">{{ item.name }}</text>
    </view>
    </view>
    <text class="rw" qq:if="{{ num }}">还有{{ num }}个任务没完成</text>
     <text class="rw" qq:if="{{num==0}}">任务完成！</text>
     </view>
    </view>

index.qss:

     .header {
    display: flex;
     align-items: center;
      border: 1rpx solid #e0e0e0;
     border-radius: 10rpx;
     box-shadow: 0 0 8rpx #e0e0e0;
     margin-bottom: 30rpx;
     padding: 13rpx;
     }
     .input {
     flex: 1;
     font-size: 28rpx;
     }
    .list {
     border: 1rpx solid #e0e0e0;
    border-radius: 5srpx;
    box-shadow: 0 0 5rpx #e0e0e0;
     }
    .list.item.name {
     text-decoration: line-through;
     color: #888;
  
     }
     .box{
     display: flex;
    }
    .rw {
    display: flex;
      justify-content: space-between;
      margin: 30rpx 0;
     padding: 0 10rpx;
     font-size: 26rpx;
       color: #777;
    }
    .list .item {
      display: flex;
     align-items: center;
     padding: 25rpx;
      border-bottom: 1rpx solid #e0e0e0;
    }