Расположение: "/usr/local/bin/test_monitor_daemon.sh"
Делаем скрипт исполняемым: "sudo chmod +x /usr/local/bin/test_monitor_daemon.sh"
Далее создаем unit:
sudo nano /etc/systemd/system/test-monitor.service;
Вставляем следующее:
[Unit]
Description=Test Process Monitoring Daemon
After=network.target

[Service]
Type=simple
ExecStart=/usr/local/bin/test_monitor_daemon.sh
Restart=always

[Install]
WantedBy=multi-user.target
Сохраняем.
Перезапустим systemd
Включи автозапуск "sudo systemctl enable test-monitor.service"
И наконец запускаем "сервис sudo systemctl start test-monitor.service"
