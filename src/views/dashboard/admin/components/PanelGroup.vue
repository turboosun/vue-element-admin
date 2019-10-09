<template>
  <div>
    <el-row :gutter="12">
      <el-col :xs="12" :sm="12" :lg="12" class="card-panel-col text-left-title">待办事项</el-col>
      <el-col :xs="12" :sm="12" :lg="12" class="card-panel-col text-right-add"><i class="el-icon-circle-plus-outline" /></el-col>
    </el-row>
    <el-row :gutter="40" class="panel-group">
      <el-col :xs="12" :sm="12" :lg="6" class="card-panel-col">
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
      <el-col :xs="12" :sm="12" :lg="6" class="card-panel-col">
        <div class="card-panel" @click="handleSetLineChartData('messages')">
          <div class="card-panel-icon-wrapper icon-message">
            <svg-icon icon-class="skill" class-name="card-panel-icon" />
          </div>
          <div class="card-panel-description">
            <count-to :start-val="0" :end-val="81212" :duration="3000" class="card-panel-num" />
            <div class="card-panel-text">
              加班审批
            </div>
          </div>
        </div>
      </el-col>
      <el-col :xs="12" :sm="12" :lg="6" class="card-panel-col">
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
      <el-col :xs="12" :sm="12" :lg="6" class="card-panel-col">
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
  </div>

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
  .text-left-title{
    text-align: left;
    font-size: 18px;
    color: #303133;
  }
  .text-right-add{
    text-align: right;
  }
.panel-group {
  margin-top: 18px;
  height: 263px;
  .card-panel-col {
    margin-bottom: 32px;
  }
  .card-panel {
    /*height: 208px;*/
    cursor: pointer;
    font-size: 12px;
    position: relative;
    overflow: hidden;
    color: #666;
    background: #fff;
    box-shadow: 4px 4px 40px rgba(0, 0, 0, .05);
    border-color: rgba(0, 0, 0, .05);
    text-align: center;

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
      border-radius: 50%;
    }

    .card-panel-icon {
      /*float: left;*/
      font-size: 30px;
    }

    .card-panel-description {
      /*float: right;*/
      font-weight: bold;
      /*margin: 26px 0;*/
      text-align: center;

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
