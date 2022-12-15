<template>
    <CommonCard title="累计用户数" value="1,087,503">
        <template v-slot:footer>
            <div class="total-users-footer">
                <span>日同比</span>
                <span class="emphasis">8.73%</span>
                <div class="increase"></div>
                <span>月同比</span>
                <span class="emphasis">8.73%</span>
                <div class="decrease"></div>
            </div>
        </template>
    </CommonCard>
</template>

<script>
import commonCardMixin from '../../mixins/commonCardMixin'
export default {
    name: 'TotalUsers',
    mixins: [commonCardMixin]
}
</script>

<style lang="scss" scoped>
.total-users-footer {
    display: flex;

    .increase {
        width: 0;
        height: 0;
        border-width: 6px;
        border-color: transparent transparent red transparent;
        border-style: solid;
        margin: 0 10px 3px 5px
    }

    .decrease {
        width: 0;
        height: 0;
        border-width: 6px;
        border-color: green transparent transparent transparent;
        border-style: solid;
        margin: 5px 0 0 5px
    }
}
</style>
