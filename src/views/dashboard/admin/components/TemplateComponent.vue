<template>
  <el-row :gutter="40" class="panel-group">
    <el-col :xs="12" :sm="12" :lg="4" class="card-panel-col">
      <div class="card-panel" @click="handleSetLineChartData('newVisitis')">
        <div class="card-panel-icon-wrapper icon-people">
          <svg-icon icon-class="guide" class-name="card-panel-icon" />
        </div>
        <div class="card-panel-description">
          <count-to :start-val="0" :end-val="102400" :duration="2600" class="card-panel-num" />
          <div class="card-panel-text">
            假期审批
          </div>
        </div>
      </div>
    </el-col>
    <el-col :xs="12" :sm="12" :lg="4" class="card-panel-col">
      <div class="card-panel" @click="handleSetLineChartData('messages')">
        <div>
          <div class="card-panel-icon-wrapper icon-message">
            <svg-icon icon-class="skill" class-name="card-panel-icon" />
          </div>
          <div class="mo-title">
            <p>模板名称</p>
            <span>适用人群</span>
          </div>
        </div>
        <p class="des">我是一行模板说明我是一行模板说明我是一行模板说明我是一行模板</p>
        <div class="card-panel-description">
          <span>使用次数：200次</span>
          <el-button class="btn" type="primary">使用模板</el-button>
        </div>
      </div>
    </el-col>
    <el-col :xs="12" :sm="12" :lg="4" class="card-panel-col">
      <div class="card-panel" @click="handleSetLineChartData('purchases')">
        <div class="card-panel-icon-wrapper icon-money">
          <svg-icon icon-class="user" class-name="card-panel-icon" />
        </div>
        <div class="card-panel-description">
          <count-to :start-val="0" :end-val="9280" :duration="3200" class="card-panel-num" />
          <div class="card-panel-text">
            合同到期
          </div>
        </div>
      </div>
    </el-col>
    <el-col :xs="12" :sm="12" :lg="4" class="card-panel-col">
      <div class="card-panel" @click="handleSetLineChartData('shoppings')">
        <div class="card-panel-icon-wrapper icon-shopping">
          <svg-icon icon-class="dashboard" class-name="card-panel-icon" />
        </div>
        <div class="card-panel-description">
          <count-to :start-val="0" :end-val="13600" :duration="3600" class="card-panel-num" />
          <div class="card-panel-text">
            生日提醒
          </div>
        </div>
      </div>
    </el-col>
  </el-row>
</template>

<script>
import CountTo from 'vue-count-to'

export default {
  components: {
    CountTo
  },
  methods: {
    handleSetLineChartData(type) {
      this.$emit('handleSetLineChartData', type)
    }
  }
}
</script>

<style lang="scss" scoped>
.panel-group {
  margin-top: 18px;
  height: 263px;
  .card-panel-col {
    margin: 36px;
    height: 263px;
    background: #FFFFFF;
    border: 1px solid #DCDFE6;
  }
  .card-panel {
    cursor: pointer;
    font-size: 12px;
    position: relative;
    overflow: hidden;
    color: #666;
    background: #fff;
    box-shadow: 4px 4px 40px rgba(0, 0, 0, .05);
    border-color: rgba(0, 0, 0, .05);
    .mo-title{
       display: inline-block;
       margin-left: 13px;
       font-size: 14px;
       color: #303133;
       span{
         font-size: 13px;
         color: #303133;
       }
      .btn{
        float: right;
      }
     }
    .des{
      font-size: 13px;
      color: #909399;
    }
    &:hover {
      .card-panel-icon-wrapper {
        color: #fff;
      }

      .icon-people {
        color: #fff;
        background: #1B94C6;
      }

      .icon-message {
        background: #E6A23D;
      }

      .icon-money {
        background: #F56C6C;
      }

      .icon-shopping {
        background: #F56C6C
      }
    }

    .icon-people {
      color: #1B94C6;
      background: #C3F1FA;
    }

    .icon-message {
      color: #E6A23D;
      background: #FAECD8;
    }

    .icon-money {
      color: #F56C6C;
      background: #FDE2E2;
    }

    .icon-shopping {
      color: #F56C6C;
      background: #FDE2E2;
    }

    .card-panel-icon-wrapper {
      /*float: left;*/
      display: inline-block;
      margin: 14px 0;
      padding: 15px;
      transition: all 0.38s ease-out;
      text-align: center;
      /*border-radius: 50%;*/
    }

    .card-panel-icon {
      /*float: left;*/
      font-size: 30px;
    }

    .card-panel-description {
      font-weight: bold;
      span{
        font-size: 14px;
        color: #909399;
        font-weight: normal;
      }
      .card-panel-text {
        line-height: 18px;
        font-size: 16px;
        color: #E6A23D;
        margin: 20px 0;
      }

      .card-panel-num {
        font-size: 36px;
        color: #303133;
        margin: 30px 0;
      }
    }
  }
}

@media (max-width:550px) {
  .card-panel-description {
    display: none;
  }

  .card-panel-icon-wrapper {
    float: none !important;
    width: 100%;
    height: 100%;
    margin: 0 !important;

    .svg-icon {
      display: block;
      margin: 14px auto !important;
      float: none !important;
    }
  }
}
</style>
