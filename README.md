# modal-window
Открытие/закрытие модального окна
Модальное окно с формой заявки открывается по клику на кнопку "Заказать услугу". Для того чтобы скрипт сработал необходимо добавить в разметку специальные атрибуты, по которым скрипт ищет элементы:

data-modal-open - на кнопку открытия модального окна.
data-modal-close - на кнопку закрытия модального окна.
data-modal - на бекдроп модального окна.
После чего, перед закрывающим тегом body добавить тег script со ссылкой на файл скрипта для модально окна. Можно посмотреть видео-инструкцию.

<body>
  <!-- Вся твоя разметка, включая разметку модалки -->

  <!-- Ставим перед закрывающим тегом body -->
  <script src="./js/modal.js"></script>
</body>
Скрипт который необходимо скопировать и вставить в файл modal.js.

(() => {
  const refs = {
    openModalBtn: document.querySelector('[data-modal-open]'),
    closeModalBtn: document.querySelector('[data-modal-close]'),
    modal: document.querySelector('[data-modal]'),
  };

  refs.openModalBtn.addEventListener('click', toggleModal);
  refs.closeModalBtn.addEventListener('click', toggleModal);

  function toggleModal() {
    refs.modal.classList.toggle('is-hidden');
  }
})();

ссылка на видео по подключению:
https://drive.google.com/file/d/1yasixN2K-9DdsYtKCJWVay9WbyTZai0t/view?usp=sharing