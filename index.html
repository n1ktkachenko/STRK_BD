<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <title>Коллабы Bitrix24</title>

  <!-- ✅ Подключение официальных стилей Bitrix24 -->
  <link rel="stylesheet" href="https://cdn.bitrix24.site/bitrix/js/ui/design-tokens/dist/ui.design-tokens.min.css">
  <link rel="stylesheet" href="https://cdn.bitrix24.site/bitrix/js/ui/buttons/dist/ui.buttons.bundle.min.css">
  <link rel="stylesheet" href="https://cdn.bitrix24.site/bitrix/js/ui/notification/ui.notification.min.css">

  <style>
    body {
      font-family: "Open Sans", sans-serif;
      background: #f5f7fa;
      color: #333;
      margin: 0;
      padding: 20px;
    }

    h1 {
      font-size: 22px;
      margin-bottom: 20px;
    }

    .ui-btn-container {
      margin-bottom: 16px;
    }

    table {
      width: 100%;
      border-collapse: collapse;
      border: 1px solid #e1e6ea;
      background: #fff;
      border-radius: 8px;
      overflow: hidden;
    }

    th, td {
      padding: 10px 14px;
      border-bottom: 1px solid #eef2f4;
      text-align: left;
    }

    th {
      background: #f7f9fa;
      font-weight: 600;
    }

    tr:hover {
      background: #f0f6ff;
    }

    a.link {
      color: #2fc6f6;
      text-decoration: none;
    }

    a.link:hover {
      text-decoration: underline;
    }

    .empty {
      text-align: center;
      color: #999;
      padding: 20px;
    }
  </style>
</head>
<body>
  <h1>Объекты (Коллабы)</h1>

  <div class="ui-btn-container">
    <button class="ui-btn ui-btn-primary" onclick="loadCollabs()">Обновить</button>
    <button class="ui-btn ui-btn-success" onclick="openAddForm()">+ Создать</button>
  </div>

  <table id="table">
    <thead>
      <tr>
        <th>Название</th>
        <th>Руководитель</th>
        <th>Дата создания</th>
        <th>Тип</th>
      </tr>
    </thead>
    <tbody><tr><td colspan="4" class="empty">Загрузка...</td></tr></tbody>
  </table>

  <!-- ✅ SDK Bitrix24 -->
  <script src="https://api.bitrix24.com/api/v1/"></script>

  <script>
    BX24.init(() => {
      console.info("✅ Приложение инициализировано через GitHub Pages");
      loadCollabs();
    });

    // 📋 Загрузка списка коллабов (проектов)
    function loadCollabs() {
      BX24.callMethod('sonet_group.get', { FILTER: { PROJECT: 'Y' } }, (res) => {
        if (res.error()) {
          BX.UI.Notification.Center.notify({ content: 'Ошибка: ' + res.error().error_description });
          console.error(res.error());
          return;
        }

        const groups = res.data() || [];
        const tbody = document.querySelector("#table tbody");
        tbody.innerHTML = '';

        if (!groups.length) {
          tbody.innerHTML = <tr><td colspan="4" class="empty">Коллаб не найдено</td></tr>;
          return;
        }

        groups.forEach(g => {
          const date = g.DATE_CREATE ? new Date(g.DATE_CREATE).toLocaleDateString() : '';
          const link = <a class="link" href="https://${location.hostname}/online/?IM_COLLAB=${g.ID}" target="_blank">${g.NAME}</a>;
          const type = g.PROJECT === 'Y' ? 'Коллаба' : 'Группа';
          const row = `
            <tr>
              <td>${link}</td>
              <td>${g.OWNER_ID || ''}</td>
              <td>${date}</td>
              <td>${type}</td>
            </tr>`;
          tbody.insertAdjacentHTML('beforeend', row);
        });
      });
    }

    // 🧩 Окно добавления нового объекта
    function openAddForm() {
      BX.UI.Dialogs.MessageBox.show({
        title: "Создание нового объекта",
        message: `
          <input id="objName" class="ui-ctl-element" placeholder="Название объекта"><br><br>
          <input id="objExec" class="ui-ctl-element" placeholder="Руководитель (ФИО или ID)"><br><br>
          <input id="objDate" type="date" class="ui-ctl-element" placeholder="Дата сдачи">`,
        buttons: BX.UI.Dialogs.MessageBoxButtons.OK_CANCEL,
        onOk: function(box) {
          const name = document.getElementById('objName').value.trim();
          const exec = document.getElementById('objExec').value.trim();
          const date = document.getElementById('objDate').value;
          if (!name) {
            BX.UI.Notification.Center.notify({ content: 'Введите название объекта' });
            return;
          }
          addProjectToList(name, exec, date);
          box.close();
        }
      });
    }

    // 🗂 Добавление объекта в список Bitrix
    function addProjectToList(name, responsible, date) {
      BX24.callMethod('lists.element.add', {
        IBLOCK_TYPE_ID: 'lists',
        IBLOCK_ID: 28, // ← замените на ID вашего списка в Bitrix
        ELEMENT_CODE: name,
        FIELDS: {
          'NAME': name,
          'PROPERTY_123': responsible,
          'PROPERTY_124': date
        }
      }, function(res) {
        if (res.error()) {
          BX.UI.Notification.Center.notify({ content: 'Ошибка: ' + res.error().error_description });
        } else {
          BX.UI.Notification.Center.notify({ content: '✅ Объект добавлен в список' });
          loadCollabs();
        }
      });
    }
  </script>
</body>
</html>
