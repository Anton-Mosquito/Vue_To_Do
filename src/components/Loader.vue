<template>
    <div class="cssload-loading">
        <i></i>
        <i></i>
        <i></i>
    </div>
</template>


<style scoped>
.cssload-loading {
	position: absolute;
	left: 50%;
    top: 60%;
	width: 60px;
	height: 60px;
	margin: -30px 0 0 -30px;
}

.cssload-loading i {
	position: absolute;
	top: 60px; left: 60px;
	display: block;
	width: 60px;
	height: 60px;
	background: rgb(121,158,210);
	border-radius: 60px;
	animation: cssload-spin2 1.73s ease-in-out infinite;
}
.cssload-loading i:first-child {
	top: -60px; left: 0;
	background: rgb(25,70,133);
	animation: cssload-spin 1.73s ease-in-out infinite;
}
.cssload-loading i:last-child {
	top: 60px; left: -60px;
	background: rgb(199,32,44);
	animation: cssload-spin3 1.73s ease-in-out infinite;
}






@keyframes cssload-spin {
	0% {
		top: -60px;
		left: 0;
		transform: scale(1);
	}
	17% {
		transform: scale(.5);
	}
	33% {
		top: 60px;
		left: 60px;
		transform: scale(1);
	}
	50% {
		transform: scale(.5);
	}
	66% {
		top: 60px;
		left: -60px;
		transform: scale(1);
	}
	83% {
		transform: scale(.5);
	}
	100% {
		top: -60px;
		left: 0;
		transform: scale(1);
	}
}

@keyframes cssload-spin2 {
	0% {
		top: 60px;
		left: 60px;
		transform: scale(1);
	}
	17% {
		transform: scale(.5);
	}
	33% {
		top: 60px;
		left: -60px;
		transform: scale(1);
	}
	50% {
		transform: scale(.5);
	}
	66% {
		top: -60px;
		left: 0;
		transform: scale(1);
	}
	83% {
		transform: scale(.5);
	}
	100% {
		top: 60px;
		left: 60px;
		transform: scale(1);
	}
}

@keyframes cssload-spin3 {
	0% {
		top: 60px;
		left: -60px;
		transform: scale(1);
	}
	17% {
		transform: scale(.5);
	}
	33% {
		top: -60px;
		left: 0;
		transform: scale(1);
	}
	50% {
		transform: scale(.5);
	}
	66% {
		top: 60px;
		left: 60px;
		transform: scale(1);
	}
	83% {
		transform: scale(.5);
	}
	100% {
		top: 60px;
		left: -60px;
		transform: scale(1);
	}
}
</style>