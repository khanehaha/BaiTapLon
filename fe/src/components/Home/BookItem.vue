<script>
export default {
    name: 'BookItem',
    props: {
        data: {
            type: Object,
            required: true,
        },
    },
    methods: {
        handleNavigate() {
            this.$router.push({
                name: 'book',
                params: {
                    id: data.masach,
                },
            });
        },
    },
};
</script>

<template>
    <div class="BookItem m-2">
        <img :src="data.image" alt="" class="image" />
        <div class="d-flex justify-content-between align-items-center p-4">
            <div class="d-flex align-items-start justify-content-center flex-column">
                <h5 class="m-0 title">
                    <router-link :to="`/book/${data.masach}`">
                        {{ data.tensach }}
                    </router-link>
                </h5>
                <span class="author">{{ data.tacgia }}</span>
                <p class="pay">
                    Đơn giá: <span>{{ data.dongia }} đ</span>
                </p>
                <p class="quantity">
                    Số lượng: <span>{{ data?.soquyen - data?.soquyendamuon || 0 }}</span>
                </p>
            </div>
        </div>
    </div>
</template>

<style lang="scss">
.BookItem {
    box-shadow:  rgba(224, 35, 158, 0.316) 0px 6px 24px 0px, rgba(74, 6, 134, 0.08) 0px 0px 0px 1px;
    height: 360px;
    max-width: 190px;
    display: flex;
    flex-direction: column;

    .image {
        width: 190px;
        height: 190px;
    }

    .title {
        min-height: 40px;
        font-size: 16px;
        overflow: hidden;
        display: -webkit-box;
        -webkit-line-clamp: 2; /* number of lines to show */
        line-clamp: 2;
        -webkit-box-orient: vertical;
    }
    .author {
        font-size: 12px;
        color: #d18ea6;
        overflow: hidden;
        display: -webkit-box;
        -webkit-line-clamp: 1; /* number of lines to show */
        line-clamp: 1;
        -webkit-box-orient: vertical;
    }

    .pay {
        font-size: 14px;
        margin-top: 4px;
        span {
            color: #fe642e;
            font-weight: 600;
            font-size: 16px;
        }
    }

    .quantity {
        font-size: 12px;
        margin: 0px 0 0 0;
        span {
            font-size: 16px;
            font-weight: 600;
        }
    }
}
</style>
